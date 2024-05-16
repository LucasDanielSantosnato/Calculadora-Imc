esta calculadora e para saber se o seu peso esta na media, se vc esta acima do peso ou se vc esta abaixo da media de peso normal(padronizado).
# Calculadora-Imc
ela calcula o seu peso e sua altura para saber se seu peso esta na media de acordo com sua altura também.
este é o código utilizado para fazer ela 👉🏼
utilizei o html que é oque tem no meu site , e usei o css para estilizar e organizar e modelar o meu site:
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calculadora de IMC</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        background-color: #0f3057; 
        color: #fff; 
    }

    .calculator {
        background-color: #173f5f;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        text-align: center;
    }

    input[type="text"],
    input[type="number"] {
        width: 80px;
        padding: 8px;
        margin: 0 5px;
        text-align: center;
    }

    button {
        padding: 10px 20px;
        background-color: #20639b;
        border: none;
        color: #fff;
        cursor: pointer;
        border-radius: 5px;
    }

    button:hover {
        background-color: #007bff;
    }

    #result {
        margin-top: 20px;
    }
</style>
</head>
<body>
<div class="calculator">
    <h2>Calculadora de IMC</h2>
    <label for="name">Nome:</label>
    <input type="text" id="name">
    <br>
    <label for="weight">Peso (kg):</label>
    <input type="number" id="weight" step="0.01">
    <br>
    <label for="height">Altura (m):</label>
    <input type="number" id="height" step="0.01">
    <br>
    <button onclick="calculateIMC()">Calcular</button>
    <div id="result"></div>
</div>

<script>
    function calculateIMC() {
        var name = document.getElementById('name').value;
        var weight = parseFloat(document.getElementById('weight').value);
        var height = parseFloat(document.getElementById('height').value);
        
        if (name.trim() === '' || isNaN(weight) || isNaN(height) || weight <= 0 || height <= 0) {
            document.getElementById('result').innerHTML = 'Por favor, insira valores válidos.';
            return;
        }
        
        var imc = weight / (height * height);
        var message = name + ', seu IMC é ' + imc.toFixed(2) + '. ';

        if (imc < 18.5) {
            message += 'Você está abaixo do peso.';
        } else if (imc < 25) {
            message += 'Você está com o peso normal.';
        } else if (imc < 30) {
            message += 'Você está com sobrepeso.';
        } else {
            message += 'Você está obeso.';
        }
        
        document.getElementById('result').innerHTML = message;
    }
</script>
</body>
</html>

