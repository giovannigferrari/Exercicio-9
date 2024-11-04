<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>8Manipulação de Valores</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        input, button {
            padding: 10px;
            margin: 5px;
        }
        .result {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Inserção de Valores</h1>
    <label for="valor">Insira um valor:</label>
    <input type="number" id="valor" placeholder="Digite um valor" />
    <button onclick="adicionarValor()">Adicionar Valor</button>
    <div class="result">
        <p><strong>Valores inseridos:</strong> <span id="valoresInseridos"></span></p>
    </div>
    <button onclick="mostrarValores()">Mostrar Todos os Valores</button>
    <button onclick="mostrarMaiorValor()">Mostrar Maior Valor</button>
    <button onclick="mostrarMenorValor()">Mostrar Menor Valor</button>
    <div class="result">
        <p><strong>Resultado:</strong> <span id="resultado"></span></p>
    </div>
    <script>
        let valores = [];
        function adicionarValor() {
            const valor = parseFloat(document.getElementById('valor').value);
            if (isNaN(valor)) {
                alert("Por favor, insira um valor válido.");
                return;
            }
            valores.push(valor);
            document.getElementById('valor').value = '';
            document.getElementById('valoresInseridos').textContent = valores.join(', ');
        }
        function mostrarValores() {
            if (valores.length === 0) {
                alert("Nenhum valor foi inserido ainda.");
                return;
            }
            document.getElementById('resultado').textContent = "Todos os valores: " + valores.join(', ');
        }
        function mostrarMaiorValor() {
            if (valores.length === 0) {
                alert("Nenhum valor foi inserido ainda.");
                return;
            }
            const maiorValor = Math.max(...valores);
            document.getElementById('resultado').textContent = "Maior valor: " + maiorValor;
        }
        function mostrarMenorValor() {
            if (valores.length === 0) {
                alert("Nenhum valor foi inserido ainda.");
                return;
            }
            const menorValor = Math.min(...valores);
            document.getElementById('resultado').textContent = "Menor valor: " + menorValor;
        }
    </script>
</body>
</html>
 

 
