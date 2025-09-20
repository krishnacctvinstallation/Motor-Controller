<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Motor Controller Login</title>
  <style>
    body, html {
      margin: 0;
      padding: 0;
      height: 100%;
      font-family: sans-serif;
    }

    .login-section {
      background-image: url('login_background.png'); /* <-- tamari image */
      background-size: cover;
      background-position: center;
      height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    .box {
      max-width: 300px;
      width: 100%;
      padding: 20px;
      background: rgba(255,255,255,0.9);
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.3);
      text-align: center;
    }

    input, button {
      width: 100%;
      margin: 8px 0;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 14px;
    }

    button {
      background: #2b7cff;
      color: white;
      border: none;
      cursor: pointer;
    }

    button:hover {
      background: #1a5bcc;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <!-- Login Section -->
  <div class="login-section" id="loginSection">
    <div class="box">
      <h2>Login</h2>
      <input type="text" id="username" placeholder="Username" required />
      <input type="password" id="password" placeholder="Password" required />
      <button onclick="login()">Login</button>
      <p id="error" style="color: red;"></p>
    </div>
  </div>

  <!-- Control Section -->
  <div class="login-section hidden" id="controlSection">
    <div class="box">
      <h2>Motor Controller</h2>
      <button onclick="motorOn()">🟢 Motor ON</button>
      <button onclick="motorOff()">🔴 Motor OFF</button>
      <button onclick="v1()">⚡ V1 Phase Live Voltage</button>
    </div>
  </div>

  <script>
    const correctUser = "ahir";
    const correctPass = "12345";

    function login() {
      const user = document.getElementById("username").value;
      const pass = document.getElementById("password").value;

      if (user === correctUser && pass === correctPass) {
        document.getElementById("loginSection").classList.add("hidden");
        document.getElementById("controlSection").classList.remove("hidden");
      } else {
        document.getElementById("error").innerText = "❌ Incorrect Username or Password!";
      }
    }

    function motorOn() {
      alert("✅ Motor ON command sent!");
    }

    function motorOff() {
      alert("⛔ Motor OFF command sent!");
    }

    function v1() {
      alert("⚡ V1 phase live voltage reading...");
    }
  </script>
</body>
</html>
