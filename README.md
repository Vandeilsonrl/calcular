# calcular
operação de valores


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora Simples</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        .calculator {
            background: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            text-align: center;
            width: 300px;
        }
        .calculator input {
            width: 90%;
            margin: 10px 0;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }
        .calculator button {
            margin: 5px;
            padding: 10px 20px;
            font-size: 16px;
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .calculator button:hover {
            background-color: #0056b3;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <h1>Calculadora</h1>
        <input type="number" id="num1" placeholder="Digite o primeiro número">
        <input type="number" id="num2" placeholder="Digite o segundo número">
        <div>
            <button onclick="calculate('add')">+</button>
            <button onclick="calculate('subtract')">-</button>
            <button onclick="calculate('multiply')">×</button>
            <button onclick="calculate('divide')">÷</button>
        </div>
        <div class="result" id="result"></div>
    </div>

    <script>
        function calculate(operation) {
            const num1 = parseFloat(document.getElementById('num1').value);
            const num2 = parseFloat(document.getElementById('num2').value);
            let result;

            if (isNaN(num1) || isNaN(num2)) {
                result = 'Por favor, insira números válidos.';
            } else {
                switch (operation) {
                    case 'add':
                        result = num1 + num2;
                        break;
                    case 'subtract':
                        result = num1 - num2;
                        break;
                    case 'multiply':
                        result = num1 * num2;
                        break;
                    case 'divide':
                        result = num2 !== 0 ? num1 / num2 : 'Divisão por zero não é permitida.';
                        break;
                }
            }
            document.getElementById('result').textContent = `Resultado: ${result}`;
        }
    </script>
</body>
</html>
