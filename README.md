# calculadora-carca-a<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
        }

        .calculator {
            text-align: center;
            border: 1px solid #ccc;
            padding: 10px;
            border-radius: 5px;
            width: 300px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            grid-gap: 5px;
        }

        button {
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
        }

        #display {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
            font-size: 20px;
        }
    </style>
    <title>Calculadora</title>
</head>
<body>

    <div class="calculator">
        <input type="text" id="display" readonly>
        <div class="buttons">
            <button onclick="appendNumber('7')">7</button>
            <button onclick="appendNumber('8')">8</button>
            <button onclick="appendNumber('9')">9</button>
            <button onclick="appendOperator('/')">/</button>
           
            <button onclick="appendNumber('4')">4</button>
            <button onclick="appendNumber('5')">5</button>
            <button onclick="appendNumber('6')">6</button>
            <button onclick="appendOperator('*')">*</button>
           
            <button onclick="appendNumber('1')">1</button>
            <button onclick="appendNumber('2')">2</button>
            <button onclick="appendNumber('3')">3</button>
            <button onclick="appendOperator('-')">-</button>
           
            <button onclick="appendNumber('0')">0</button>
            <button onclick="appendOperator('.')">.</button>
            <button onclick="calculate()">=</button>
            <button onclick="appendOperator('+')">+</button>
        </div>
    </div>

    <script>
        let display = document.getElementById('display');

        function appendNumber(num) {
            display.value += num;
        }

        function appendOperator(operator) {
            display.value += operator;
        }

        function calculate() {
            try {
                display.value = eval(display.value);
            } catch (error) {
                display.value = 'Error';
            }
        }
    </script>
</body>
</html>

