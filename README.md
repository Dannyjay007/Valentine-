<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Will You Be My Valentine?</title>
  <link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <style>
    /* Background with fun colors */
    body {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(45deg, #ff758c, #ff7eb3);
      font-family: 'Roboto', sans-serif;
      overflow: hidden;
    }
    
    /* Container box */
    .container {
      background: rgba(255, 255, 255, 0.9);
      padding: 40px;
      border-radius: 20px;
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
      text-align: center;
      animation: fadeIn 1s ease-in-out;
      position: relative;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.9); }
      to { opacity: 1; transform: scale(1); }
    }

    /* Teddy bear image */
    .teddy {
      width: 120px;
      margin-bottom: 20px;
    }

    /* Heading */
    h1 {
      font-family: 'Pacifico', cursive;
      color: #ff4081;
      font-size: 2em;
    }

    /* Button container */
    .buttons {
      margin-top: 20px;
      position: relative;
    }

    /* General button styling */
    button {
      font-size: 1.2em;
      padding: 12px 25px;
      border: none;
      cursor: pointer;
      border-radius: 10px;
      transition: all 0.3s ease;
    }

    /* Yes button */
    .yes-btn {
      background-color: #e91e63;
      color: #fff;
    }

    .yes-btn:hover {
      background-color: #c2185b;
    }

    /* No button */
    .no-btn {
      background-color: #9e9e9e;
      color: #fff;
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      transition: transform 0.3s ease-in-out;
    }

    /* Celebration screen */
    .celebration {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      color: #fff;
      font-size: 2.5em;
      z-index: 10;
      text-align: center;
      font-family: 'Pacifico', cursive;
      display: none;
    }

    /* Floating hearts */
    .heart-float {
      position: absolute;
      color: #ff4081;
      font-size: 20px;
      animation: floatUp 5s linear infinite;
    }

    @keyframes floatUp {
      0% { transform: translateY(0); opacity: 1; }
      100% { transform: translateY(-100vh); opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Teddy bear image -->
    <img src="https://tinypic.host/image/IMG-0841.2xfJ4X" alt="Teddy Bear" class="teddy">
    
    <h1>Oluwafolakemi Esther, will you be my Valentine? ❤️</h1>
    
    <div class="buttons">
      <button class="yes-btn" onclick="celebrate()">Yes</button>
      <button class="no-btn" id="no-btn" onmouseover="moveNo()">No</button>
    </div>
  </div>
  
  <div class="celebration" id="celebration">
    <h2>Yay! You said YES! ❤️🎉</h2>
  </div>
  
  <script>
    function celebrate() {
      document.querySelector('.container').style.display = 'none';
      document.getElementById("celebration").style.display = "flex";
      setInterval(createHeart, 300);
    }
    
    function createHeart() {
      const heart = document.createElement("div");
      heart.innerHTML = "❤️";
      heart.classList.add("heart-float");
      document.body.appendChild(heart);
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 10 + "px";
      heart.style.animationDuration = Math.random() * 3 + 2 + "s";
      setTimeout(() => { heart.remove(); }, 5000);
    }
    
    function moveNo() {
      const button = document.getElementById("no-btn");
      let maxWidth = window.innerWidth - 200;
      let maxHeight = window.innerHeight - 100;
      let randomX = Math.random() * maxWidth;
      let randomY = Math.random() * maxHeight;
      button.style.transform = `translate(${randomX - window.innerWidth / 2}px, ${randomY - window.innerHeight / 2}px)`;
    }
  </script>
</body>
</html>
