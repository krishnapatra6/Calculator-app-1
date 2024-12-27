<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f3f3f3;
        }

        .calculator {
            width: 300px;
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            padding: 20px;
        }

        .display {
            width: 100%;
            height: 50px;
            margin-bottom: 20px;
            border: none;
            border-radius: 5px;
            background: #f9f9f9;
            text-align: right;
            padding: 10px;
            font-size: 1.5em;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }

        button {
            width: 100%;
            height: 50px;
            font-size: 1.2em;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            background-color: #e0e0e0;
            transition: background 0.2s;
        }

        button:hover {
            background-color: #d4d4d4;
        }

        .special {
            background-color: #a0d3ff;
        }

        .special:hover {
            background-color: #90c2e6;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <input type="text" class="display" id="display" disabled>
        <div class="buttons">
            <button onclick="clearDisplay()">C</button>
            <button onclick="addToDisplay('%')">%</button>
            <button onclick="backspace()">⌫</button>
            <button onclick="addToDisplay('/')">÷</button>
            <button onclick="addToDisplay('7')">7</button>
            <button onclick="addToDisplay('8')">8</button>
            <button onclick="addToDisplay('9')">9</button>
            <button onclick="addToDisplay('*')">×</button>
            <button onclick="addToDisplay('4')">4</button>
            <button onclick="addToDisplay('5')">5</button>
            <button onclick="addToDisplay('6')">6</button>
            <button onclick="addToDisplay('-')">−</button>
            <button onclick="addToDisplay('1')">1</button>
            <button onclick="addToDisplay('2')">2</button>
            <button onclick="addToDisplay('3')">3</button>
            <button onclick="addToDisplay('+')">+</button>
            <button onclick="addToDisplay('00')">00</button>
            <button onclick="addToDisplay('0')">0</button>
            <button onclick="addToDisplay('.')">.</button>
            <button class="special" onclick="calculate()">=</button>
        </div>
    </div>

    <script>
        function addToDisplay(value) {
            document.getElementById('display').value += value;
        }

        function clearDisplay() {
            document.getElementById('display').value = '';
        }

        function backspace() {
            let display = document.getElementById('display');
            display.value = display.value.slice(0, -1);
        }

        function calculate() {
            let display = document.getElementById('display');
            try {
                display.value = eval(display.value);
            } catch (e) {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>
