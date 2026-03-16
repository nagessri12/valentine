<!DOCTYPE html>
<html>
<head>
  <title>Username Verification</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
      background: linear-gradient(45deg, #ff9a9e, #fecfef, #ff9a9e);
      perspective: 1000px;
    }
    #box {
      border: 2px solid #ff4081;
      padding: 20px;
      display: inline-block;
      background-color: #fff0f6;
      border-radius: 10px;
    }
    input {
      padding: 10px;
      margin: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 5px;
      background-color: #ff4081;
      color: white;
      cursor: pointer;
    }
    #message {
      margin-top: 15px;
      font-weight: bold;
    }
    .butterflies {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      pointer-events: none;
      z-index: -1;
    }
    .butterfly {
      position: absolute;
      width: 20px;
      height: 20px;
      background: transparent;
      animation: fly 15s infinite linear;
    }
    .butterfly::before, .butterfly::after {
      content: '';
      position: absolute;
      width: 10px;
      height: 15px;
      background: #ff00ff;
      border-radius: 50% 50% 0 0;
      box-shadow: 0 0 5px #ff00ff, 0 0 10px #ff00ff, 0 0 15px #ff00ff;
    }
    .butterfly::before {
      left: 0;
      transform: rotate(-30deg);
    }
    .butterfly::after {
      right: 0;
      transform: rotate(30deg);
    }
    @keyframes fly {
      0% { transform: translate(0, 0) rotateY(0deg) rotateX(0deg); }
      25% { transform: translate(100vw, 20vh) rotateY(90deg) rotateX(10deg); }
      50% { transform: translate(50vw, 50vh) rotateY(180deg) rotateX(0deg); }
      75% { transform: translate(0vw, 80vh) rotateY(270deg) rotateX(-10deg); }
      100% { transform: translate(100vw, 100vh) rotateY(360deg) rotateX(0deg); }
    }
  </style>
</head>
<body>
  <div id="box">
    <h2>Username Verification 🔐</h2>
    <input type="text" id="username" placeholder="Enter your username">
    <br>
    <button onclick="verify()">Verify</button>
    <a href="angel.html"> </a>
    <p id="message"></p>
  </div>

  <div class="butterflies">
    <div class="butterfly" style="animation-delay: 0s;"></div>
    <div class="butterfly" style="animation-delay: 2s;"></div>
    <div class="butterfly" style="animation-delay: 4s;"></div>
    <div class="butterfly" style="animation-delay: 6s;"></div>
    <div class="butterfly" style="animation-delay: 8s;"></div>
  </div>

  <script>
    function verify() {
      const input = document.getElementById("username").value;
      const message = document.getElementById("message");

      // Correct username set here
      const correctUsername = "moni";

      if (input === correctUsername) {
        message.style.color = "green";
        message.textContent = "✅ Verification Successful! Welcome, Valentine!";
        setTimeout(() => window.location.href = "angel.html", 2000);
      } else {
        message.style.color = "red";
        message.textContent = "❌ Invalid Username. Please try again.";
      }
    }
  </script>
</body>
</html>
