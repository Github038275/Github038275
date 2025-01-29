<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Menu Cheats</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: black;
      color: white;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .container {
      background: #333;
      width: 300px;
      border-radius: 10px;
      padding: 15px;
      text-align: center;
    }
    .title {
      font-size: 20px;
      margin-bottom: 10px;
      color: #ff007f;
    }
    .slider-container {
      margin: 10px 0;
    }
    .slider {
      width: 100%;
      -webkit-appearance: none;
      height: 8px;
      border-radius: 5px;
      background: linear-gradient(to right, yellow, red);
      outline: none;
      transition: background 0.3s;
    }
    .slider::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 15px;
      height: 15px;
      border-radius: 50%;
      background: #fff;
      cursor: pointer;
    }
    .cheats {
      margin: 15px 0;
      background: #222;
      padding: 10px;
      border-radius: 10px;
    }
    .cheats h3 {
      color: #ff007f;
      margin-bottom: 10px;
    }
    .cheats .options {
      display: flex;
      justify-content: space-between;
    }
    .cheats .column {
      width: 48%;
    }
    .cheats label {
      display: block;
      margin: 5px 0;
    }
    .footer {
      display: flex;
      justify-content: space-between;
      margin-top: 10px;
      align-items: center;
    }
    .footer .image-container {
      text-align: center;
    }
    .footer img {
      width: 50px;
      height: 50px;
      border-radius: 5px;
      display: block;
      margin: 0 auto 5px;
    }
    .footer a {
      display: inline-block;
      padding: 5px 10px;
      color: white;
      background: #ff007f;
      border-radius: 5px;
      text-decoration: none;
      font-size: 12px;
    }
    .footer a:hover {
      background: #ff3399;
    }
    .dropdown {
      margin-top: 15px;
    }
    .dropdown select {
      padding: 5px;
      border-radius: 5px;
      border: none;
      background: #444;
      color: white;
      font-size: 14px;
    }
    .notification {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      background: #ff007f;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
      opacity: 0;
      visibility: hidden;
      transition: opacity 0.5s, visibility 0.5s;
    }
    .notification.show {
      opacity: 1;
      visibility: visible;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="title">@LUXECHEATS - v2.0</div>
    <div class="slider-container">
      <input id="slider" type="range" min="0" max="100" value="50" class="slider" oninput="updateSliderColor(this)">
    </div>
    <div class="cheats">
      <h3>CHEATS</h3>
      <div class="options">
        <div class="column">
          <label><input type="checkbox" onchange="notifyActivation('AimNeck')"> AimNeck</label>
          <label><input type="checkbox" onchange="notifyActivation('Precision')"> Precision</label>
          <label><input type="checkbox" onchange="notifyActivation('AimLock')"> AimLock</label>
          <label><input type="checkbox" onchange="notifyActivation('ForceDPI')"> ForceDPI</label>
        </div>
        <div class="column">
          <label><input type="checkbox" onchange="notifyActivation('Strength')"> Strength</label>
          <label><input type="checkbox" onchange="notifyActivation('AimForce')"> AimForce</label>
          <label><input type="checkbox" onchange="notifyActivation('Scope2x')"> Scope2x</label>
          <label><input type="checkbox" onchange="notifyActivation('FixSensi')"> FixSensi</label>
        </div>
      </div>
    </div>
    <div class="dropdown">
      <label for="game-version" style="color: #ff007f;">Select Version:</label>
      <select id="game-version">
        <option value="FF Max">com.dts.freefiremax</option>
        <option value="com.dts.freefireth">FF Normal</option>
      </select>
    </div>
    <div class="footer">
      <div class="image-container">
        <img src="icon1.png" alt="Icon 1">
        <a href="freefire://'" target="_blank">Freefire HT</a>
      </div>
      <div class="image-container">
        <img src="icon2.png" alt="Icon 2">
        <a href="freefire://'" target="_blank">Freefire MAX</a>
      </div>
    </div>
  </div>
  <div class="notification" id="notification"></div>

  <script>
    function updateSliderColor(slider) {
      const value = slider.value;
      slider.style.background = `linear-gradient(to right, yellow ${value}%, red ${value}%)`;
    }

    function notifyActivation(option) {
      const gameVersion = document.getElementById('game-version').value;
      const notification = document.getElementById('notification');
      notification.textContent = `${option} activated in ${gameVersion}`;
      notification.classList.add('show');
      setTimeout(() => {
        notification.classList.remove('show');
      }, 3000);
    }
  </script>
</body>
</html>
