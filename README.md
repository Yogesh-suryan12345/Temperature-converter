index.html:
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Temperature Converter</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>Temperature Converter</h1>
    <label for="celsius">Enter temperature in Celsius:</label>
    <input type="number" id="celsius" placeholder="Enter Celsius temperature">
    <button onclick="convertTemperature()">Convert</button>
    <div id="result"></div>
  </div>
  <script src="script.js"></script>
</body>
</html>
styles.css:
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.container {
  text-align: center;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
}

h1 {
  margin-top: 0;
}

input {
  padding: 5px;
  margin: 10px 0;
}

button {
  padding: 10px 20px;
  background-color: #007BFF;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

#result {
  font-size: 18px;
  font-weight: bold;
  margin-top: 20px;
}
script.js:
function convertTemperature() {
  const celsiusInput = document.getElementById("celsius");
  const celsiusValue = parseFloat(celsiusInput.value);

  if (isNaN(celsiusValue)) {
    alert("Please enter a valid temperature in Celsius.");
    return;
  }

  const fahrenheitValue = (celsiusValue * 9/5) + 32;
  const resultElement = document.getElementById("result");
  resultElement.textContent = `${celsiusValue} Celsius is equal to ${fahrenheitValue.toFixed(2)} Fahrenheit.`;
}
