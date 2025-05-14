# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Animations & LocalStorage Example</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f0f0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .container {
      text-align: center;
    }

    #animateButton {
      background-color: #4CAF50;
      color: white;
      border: none;
      padding: 15px 32px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
      transition: all 0.3s ease;
      outline: none;
    }

    @keyframes animateButton {
      0% {
        transform: scale(1);
        background-color: #4CAF50;
      }
      50% {
        transform: scale(1.1);
        background-color: #45a049;
      }
      100% {
        transform: scale(1);
        background-color: #4CAF50;
      }
    }

    #animateButton:hover {
      animation: animateButton 0.5s ease-in-out;
    }
  </style>
</head>
<body>
  <div class="container">
    <button id="animateButton">Click me!</button>
  </div>

  <script>
    const button = document.getElementById("animateButton");

    let animationPreference = localStorage.getItem("buttonHovered");

    if (!animationPreference) {
      localStorage.setItem("buttonHovered", "false");
    }

    if (animationPreference === "true") {
      button.style.pointerEvents = "none";
      button.innerText = "You’ve already seen the animation!";
    }

    button.addEventListener("click", () => {
      button.innerText = "Enjoy the animation!";
      localStorage.setItem("buttonHovered", "true");
      button.classList.add("animate");

      setTimeout(() => {
        button.classList.remove("animate");
      }, 500);
    });
  </script>
</body>
</html>

