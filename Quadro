<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dimensionamento de Quadro</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 8px;
            box-shadow: 2px 2px 10px rgba(0,0,0,0.1);
        }
        input, select, button {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            font-size: 16px;
        }
        button {
            background-color: #28a745;
            color: white;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #218838;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Dimensionamento de Quadro</h2>
        <label for="largura_quadro">Largura do Quadro (cm):</label>
        <input type="number" id="largura_quadro" placeholder="Digite a largura">
        
        <label for="tipo_modulo">Escolha o Tipo de Módulo:</label>
        <select id="tipo_modulo">
            <option value="18">X8 (18 cm)</option>
            <option value="24">Home One (24 cm)</option>
        </select>
        
        <label for="num_modulos">Quantidade de Módulos:</label>
        <input type="number" id="num_modulos" placeholder="Digite a quantidade">
        
        <button onclick="calcularDimensionamento()">Calcular</button>
        
        <h3>Resultado:</h3>
        <p id="resultado"></p>
    </div>

    <script>
        function calcularDimensionamento() {
            let larguraQuadro = parseInt(document.getElementById("largura_quadro").value);
            let larguraModulo = parseInt(document.getElementById("tipo_modulo").value);
            let numModulos = parseInt(document.getElementById("num_modulos").value);

            if (isNaN(larguraQuadro) || isNaN(larguraModulo) || isNaN(numModulos)) {
                document.getElementById("resultado").innerText = "Por favor, preencha todos os campos corretamente.";
                return;
            }
            
            const canaletaLateral = 8;
            const espacoLateral = 2;
            const espacoEntreModulos = 2;
            const alturaPrimeiraFileira = 13;
            const alturaCanaletaPrimeira = 5;
            const alturaFileiraModulos = 22;
            const alturaCanaletaEntreFileiras = 5;
            const alturaCanaletaFinal = 8;
            const alturaCanaletaInicial = 8;

            let larguraUtil = larguraQuadro - 2 * canaletaLateral - 2 * espacoLateral;
            let modulosPorFileira = Math.floor(larguraUtil / (larguraModulo + espacoEntreModulos));
            let fileiraBornesak = alturaPrimeiraFileira + alturaCanaletaPrimeira;
            let numFileirasModulos = Math.ceil(numModulos / modulosPorFileira);

            let alturaTotal = alturaCanaletaInicial + fileiraBornesak +
                numFileirasModulos * (alturaFileiraModulos + alturaCanaletaEntreFileiras) +
                alturaCanaletaFinal;

            alturaTotal = Math.ceil(alturaTotal / 10) * 10;

            document.getElementById("resultado").innerText =
                `Módulos por fileira: ${modulosPorFileira}\n` +
                `Fileiras necessárias: ${numFileirasModulos}\n` +
                `Fileira de Borne Sak: 1\n` +
                `Altura total do quadro: ${alturaTotal} cm`;
        }
    </script>
</body>
</html>
