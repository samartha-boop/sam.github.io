# sam.github.io
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Plant Monitoring System</title>
  
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #e8f5e9;
      margin: 0;
      padding: 0;
    }

    header {
      background: #2e7d32;
      color: white;
      text-align: center;
      padding: 20px;
    }

    .container {
      max-width: 700px;
      margin: 30px auto;
      padding: 20px;
    }

    .card {
      background: #ffffff;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      text-align: center;
    }

    .value {
      font-size: 38px;
      color: #2e7d32;
      margin-top: 10px;
    }

    .status {
      font-size: 22px;
      margin-top: 10px;
      font-weight: bold;
    }

    .healthy {
      color: green;
    }
    .diseased {
      color: red;
    }

    button {
      background: #2e7d32;
      color: white;
      border: none;
      padding: 10px 18px;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 10px;
      font-size: 16px;
    }

    button:hover {
      background: #1b5e20;
    }
  </style>
</head>

<body>

<header>
  <h1>🌱 Plant Monitoring Dashboard</h1>
  <p>Humidity • Temperature • Soil Moisture • Disease Detection</p>
</header>

<div class="container">

  <div class="card">
    <h2>💧 Humidity Level</h2>
    <div class="value" id="humidity">-- %</div>
    <button onclick="checkHumidity()">Check Humidity</button>
  </div>

  <div class="card">
    <h2>🌡 Temperature</h2>
    <div class="value" id="temperature">-- °C</div>
    <button onclick="checkTemperature()">Check Temperature</button>
  </div>

  <div class="card">
    <h2>🌱 Soil Moisture</h2>
    <div class="value" id="moisture">-- %</div>
    <button onclick="checkMoisture()">Check Soil Moisture</button>
  </div>

  <div class="card">
    <h2>🦠 Disease Detection</h2>
    <div class="status" id="diseaseStatus">Unknown</div>
    <button onclick="checkDisease()">Detect Disease</button>
  </div>

</div>

<script>
  function checkHumidity() {
    let humidity = Math.floor(Math.random() * 100) + 1;
    document.getElementById("humidity").innerHTML = humidity + " %";
  }

  function checkTemperature() {
    let temperature = (Math.random() * 15 + 20).toFixed(1); // 20–35°C
    document.getElementById("temperature").innerHTML = temperature + " °C";
  }

  function checkMoisture() {
    let moisture = Math.floor(Math.random() * 100) + 1;
    document.getElementById("moisture").innerHTML = moisture + " %";
  }

  function checkDisease() {
    let diseaseDetected = Math.random() > 0.7; // 30% chance
    let status = document.getElementById("diseaseStatus");

    if (diseaseDetected) {
      status.innerHTML = "⚠ Disease Detected!";
      status.className = "status diseased";
    } else {
      status.innerHTML = "✅ Plant is Healthy";
      status.className = "status healthy";
    }
  }
</script>

</body>
</html>
