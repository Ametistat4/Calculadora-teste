<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Calculakitty💗</title>
  <style>
    body {
      background: linear-gradient(135deg, #ffe6f2, #ffb6d9);
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .calc {
      width: 310px;
      background: #fff;
      padding: 20px;
      border-radius: 20px;
      box-shadow: 0 0 20px #ff8fc7;
      border: 3px solid #ffa6d1;
    }

    .kitty {
      text-align: center;
      margin-bottom: 10px;
      font-size: 20px;
      font-weight: bold;
      color: #ff4fa3;
    }

    .display {
      width: 100%;
      height: 60px;
      background: #ffe5f2;
      border: 2px solid #ff98c7;
      border-radius: 15px;
      margin-bottom: 15px;
      padding: 10px;
      font-size: 30px;
      text-align: right;
      color: #d90072;
    }

    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
    }

    button {
      padding: 18px;
      font-size: 20px;
      border: none;
      border-radius: 15px;
      background: #ffd1e6;
      color: #d90072;
      font-weight: bold;
      cursor: pointer;
      transition: 0.2s;
    }

    button:hover {
      background: #ffb5da;
    }

    .op {
      background: #ff4fa3;
      color: white;
    }

    .op:hover {
      background: #e93c90;
    }
  </style>
</head>
<body>

  <div class="calc">
    <div class="kitty"> Calculakitty </div>
    <input type="text" class="display" id="display" disabled>

    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="delChar()">⌫</button>
      <button onclick="press('%')">%</button>
      <button class="op" onclick="press('/')">÷</button>

      <button onclick="press('7')">7</button>
      <button onclick="press('8')">8</button>
      <button onclick="press('9')">9</button>
      <button class="op" onclick="press('*')">×</button>

      <button onclick="press('4')">4</button>
      <button onclick="press('5')">5</button>
      <button onclick="press('6')">6</button>
      <button class="op" onclick="press('-')">−</button>

      <button onclick="press('1')">1</button>
      <button onclick="press('2')">2</button>
      <button onclick="press('3')">3</button>
      <button class="op" onclick="press('+')">+</button>

      <button onclick="press('0')">0</button>
      <button onclick="press('.')">.</button>
      <button class="op" style="grid-column: span 2;" onclick="calculate()">=</button>
    </div>
  </div>

<script>
  let display = document.getElementById("display");

  function press(value) {
    display.value += value;
  }

  function clearDisplay() {
    display.value = "";
  }

  function delChar() {
    display.value = display.value.slice(0, -1);
  }

  function calculate() {
    try {
      display.value = eval(display.value.replace("×", "*").replace("÷", "/"));
    } catch {
      display.value = "Erro";
    }
  }
</script>

</body>
</html>
