# Simple_Calculator_App
A basic calculator web app built using HTML, CSS, and JavaScript. Performs arithmetic operations like addition, subtraction, multiplication, and division with a simple and user-friendly interface.


###html code

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic Calculator</title>
  <style>
    body {
      background-color: #f2f2f2;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      font-family: sans-serif;
    }
    .calculator {
      background: #222;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
    }
    #display {
      width: 100%;
      height: 50px;
      font-size: 24px;
      margin-bottom: 15px;
      padding: 10px;
      text-align: right;
      border: none;
      border-radius: 8px;
      outline: none;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      grid-gap: 10px;
    }
    button {
      height: 60px;
      font-size: 18px;
      border: none;
      border-radius: 8px;
      background: #444;
      color: white;
      cursor: pointer;
      transition: 0.2s;
    }
    button:hover {
      background: #666;
    }
    .equal {
      background-color: #ff9500;
    }
    .equal:hover {
      background-color: #e08b00;
    }
    .clear {
      background-color: #d11a2a;
    }
    .clear:hover {
      background-color: #aa1120;
    }
    .zero {
      grid-column: span 2;
    }
  </style>
</head>
<body>

  <div class="calculator">
    <input type="text" id="display" disabled>
    <div class="buttons">
      <button class="clear" onclick="clearDisplay()">C</button>
      <button onclick="appendValue('/')">/</button>
      <button onclick="appendValue('*')">*</button>
      <button onclick="deleteLast()">←</button>
      <button onclick="appendValue('7')">7</button>
      <button onclick="appendValue('8')">8</button>
      <button onclick="appendValue('9')">9</button>
      <button onclick="appendValue('-')">-</button>
      <button onclick="appendValue('4')">4</button>
      <button onclick="appendValue('5')">5</button>
      <button onclick="appendValue('6')">6</button>
      <button onclick="appendValue('+')">+</button>
      <button onclick="appendValue('1')">1</button>
      <button onclick="appendValue('2')">2</button>
      <button onclick="appendValue('3')">3</button>
      <button class="equal" onclick="calculateResult()">=</button>
      <button class="zero" onclick="appendValue('0')">0</button>
      <button onclick="appendValue('.')">.</button>
    </div>
  </div>

  <script>
    function appendValue(value) {
      document.getElementById("display").value += value;
    }

    function clearDisplay() {
      document.getElementById("display").value = "";
    }

    function deleteLast() {
      let display = document.getElementById("display");
      display.value = display.value.slice(0, -1);
    }

    function calculateResult() {
      let display = document.getElementById("display");
      try {
        display.value = eval(display.value);
      } catch {
        display.value = "Error";
      }
    }
  </script>
</body>
</html>




body {
  font-family: Arial, sans-serif;
  display: flex;
  height: 100vh;
  justify-content: center;
  align-items: center;
  background: #f4f4f4;
}
.calculator {
  background: #222;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.5);
}
#display {
  width: 100%;
  font-size: 2em;
  padding: 10px;
  margin-bottom: 10px;
  text-align: right;
  border: none;
  border-radius: 5px;
}
.buttons {
  display: grid;
  grid-template-columns: repeat(4, 60px);
  grid-gap: 10px;
}
button {
  padding: 20px;
  font-size: 1.2em;
  background: #333;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background: #555;
}

.zero {
  grid-column: span 2;
}


function appendValue(value) {
  document.getElementById("display").value += value;
}

function clearDisplay() {
  document.getElementById("display").value = "";
}

function deleteLast() {
  let current = document.getElementById("display").value;
  document.getElementById("display").value = current.slice(0, -1);
}

function calculateResult() {
  try {
    let result = eval(document.getElementById("display").value);
    document.getElementById("display").value = result;
  } catch (e) {
    document.getElementById("display").value = "Error";
  }
}




