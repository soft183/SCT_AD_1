<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Calculator - SkillCraft Technology</title>
  <style>
    body {
      background-color: #121212;
      color: #ffffff;
      font-family: Arial, sans-serif;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    .calculator {
      background-color: #1e1e1e;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 15px rgba(0, 255, 255, 0.2);
      width: 300px;
    }

    input[type="text"] {
      width: 100%;
      height: 60px;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      border: none;
      border-radius: 8px;
      padding: 10px;
      background-color: #2d2d2d;
      color: white;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 20px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background-color: #333;
      color: white;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    button:hover {
      background-color: #555;
    }

    .operator {
      background-color: #008080;
    }

    .operator:hover {
      background-color: #00b3b3;
    }

    .equal {
      background-color: #00cc44;
    }

    .equal:hover {
      background-color: #00e65c;
    }

    .clear {
      background-color: #cc0000;
    }

    .clear:hover {
      background-color: #ff1a1a;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" readonly>
    <div class="buttons">
      <button onclick="clearDisplay()" class="clear">C</button>
      <button onclick="append('%')" class="operator">%</button>
      <button onclick="append('/')" class="operator">÷</button>
      <button onclick="append('*')" class="operator">×</button>

      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('-')" class="operator">−</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="append('+')" class="operator">+</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button onclick="calculate()" class="equal">=</button>

      <button onclick="append('0')" style="grid-column: span 2;">0</button>
      <button onclick="append('.')">.</button>
    </div>
  </div>

  <script>
    function append(character) {
      document.getElementById('display').value += character;
    }

    function clearDisplay() {
      document.getElementById('display').value = '';
    }

    function calculate() {
      try {
        document.getElementById('display').value = eval(document.getElementById('display').value);
      } catch {
        document.getElementById('display').value = 'Error';
      }
    }
  </script>
</body>
</html>
