<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8" />
  <title>Electricity Bill Calculator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f7f7f7;
      padding: 30px;
    }
    h1 {
      margin: 0 0 16px 0;
      font-size: 20px;
    }
    .row {
      margin: 10px 0;
    }
    label {
      display: inline-block;
      width: 180px;
      font-size: 14px;
    }
    input[type="number"] {
      width: 180px;
      padding: 6px 8px;
      background: #93d4ff;
      border: 1px solid #93c7ff;
      border-radius: 3px;
      outline: none;
    }
    button {
      margin-left: 180px; 
      margin-top: 8px;
      width: 100px;
      padding: 6px 10px;
      background: #ff05c9;
      color: #ffffff;
      border: 1px solid #ff0095;
      border-radius: 3px;
      
      font-weight: bold;
    }
    

    #resultWrap {
      margin-top: 15px;
    }
    #resultLabel { font-weight: bold; }
    #result { margin-left: 6px; }
  </style>
</head>
<body>

  <div class="box">
    <h1>ELECTRICITY BILL CALCULATOR</h1>

    <div class="row">
      <label for="consumption">Power Consumption:</label>
      <input type="number" id="consumption" step="any" />
    </div>

    <div class="row">
      <label for="rate">Cost per kilowatt-hour:</label>
      <input type="number" id="rate"  step="any" />
    </div>

    <div class="row">
      <button id="calcBtn" type="button">Calculate</button>
    </div>

    <div class="row" id="resultWrap">
      <span id="resultLabel">RESULT:</span>
      <span id="result"></span>
    </div>
  </div>

  <script>
    // Directly get elements without using $
    const consumptionEl = document.getElementById('consumption');
    const rateEl = document.getElementById('rate');
    const resultEl = document.getElementById('result');
    const btn = document.getElementById('calcBtn');

    function calculateBill() {
      const kwh = parseFloat(consumptionEl.value);
      const rate = parseFloat(rateEl.value);

      if (isNaN(kwh) || isNaN(rate)) {
        resultEl.textContent = 'Please enter both values.';
        return;
      }
      const total = kwh * rate;
      resultEl.textContent = `₱ ${total.toFixed(2)}`;
    }

    btn.addEventListener('click', calculateBill);
  </script>
</body>
</html>
}
