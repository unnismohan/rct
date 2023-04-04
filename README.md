<!DOCTYPE html>
<html>
  <head>
    <title>Recruitment Tools</title>
    <style>
      body {
        font-family: Arial, sans-serif;
        background-color: #403e46;
        margin: 0;
        padding: 0;
      }
      .container {
        max-width: 550px;
        margin: 0;
        padding: 20px;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
		float: left;
		position: relative;
		left: 200px;
		top: 100px;
		
      }
	  .container1 {
        max-width: 550px;
        margin: 0;
        padding: 20px;
        background-color: #fff;
        border-radius: 5px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
		float: right;
		position: relative;
		right: 200px;
		top: 100px;
      }
      h1 {
        text-align: center;
        color: #333;
      }
      form {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-bottom: 20px;
      }
      label {
        font-weight: bold;
        margin-bottom: 10px;
      }
      input[type="number"] {
        padding: 10px;
        border-radius: 5px;
        border: none;
        margin-bottom: 20px;
        width: 100%;
        box-shadow: inset 0 0 5px rgba(0,0,0,0.1);
        font-size: 16px;
        color: #555;
      }
      input[type="number"]:focus {
        outline: none;
        box-shadow: inset 0 0 5px #007bff;
      }
      button {
        padding: 10px;
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: all 0.3s ease-in-out;
        width: 100%;
      }
      button:hover {
        background-color: #0062cc;
      }
      .calculator-result {
        text-align: center;
        font-weight: bold;
        font-size: 24px;
        color: #007bff;
        margin-top: 20px;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <h1>Expected CTC Calculator</h1>
      <form>
        <label for="current-ctc">Current CTC (LPA):</label>
        <input type="number" id="current-ctc" name="current-ctc"><br>
        <label for="percentage-increase">Percentage Increase (%):</label>
        <input type="number" id="percentage-increase" name="percentage-increase"><br>
        <button type="button" onclick="calculateExpected()">Calculate Expected CTC</button>
      </form>
      <div id="expected-ctc" class="calculator-result"></div>
    </div>
	
    <div class="container1">
      <h1>Percentage Increase Calculator</h1>
      <form>
        <label for="current-ctc">Current CTC (LPA):</label>
        <input type="number" id="current-ctc1" name="current-ctc"><br>
        <label for="expectedctc">Expected CTC (LPA)</label>
        <input type="number" id="expected-ctc1" name="expected-ctc"><br>
        <button type="button" onclick="calculatePercentage()">Percentage Increase (%)</button>
      </form>
      <div id="percentageincrease1" class="calculator-result"></div>
    </div>
    <script>
      function calculateExpected() {
        let currentCTC = document.getElementById("current-ctc").value;
        let percentageIncrease = document.getElementById("percentage-increase").value;
        let expectedCTC = currentCTC * (1 + percentageIncrease / 100);
        document.getElementById("expected-ctc").innerHTML = "Expected CTC: " + expectedCTC.toFixed(2) + " LPA" + " (" + (expectedCTC * 100000).toFixed(2) + " INR)";
      }
	  function calculatePercentage() {
        let currentCTC = document.getElementById("current-ctc1").value;
        let expectedctc = document.getElementById("expected-ctc1").value;
        let percentageincrease = ((expectedctc - currentCTC)/currentCTC) * 100
        document.getElementById("percentageincrease1").innerHTML = "Percentage Increase: " + percentageincrease.toFixed(2) + " %" ;
      }
	  
    </script>
  </body>
</html>
