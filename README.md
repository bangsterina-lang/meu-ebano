# meu-ebano
versao-final-finalizada-300-acabada
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Feliz Dia dos Namorados! ❤️</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: #ffb3c6;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            overflow: hidden;
            position: relative;
        }

        .heart-bg {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart-particle {
            position: absolute;
            bottom: -20px;
            color: #ff4d6d;
            font-size: 20px;
            opacity: 0.7;
            animation: floatUp 6s linear infinite;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) translateX(0) rotate(0deg); opacity: 0.8; }
            100% { transform: translateY(-105vh) translateX(50px) rotate(360deg); opacity: 0; }
        }

        .topo-direito-img {
            position: fixed;
            top: 20px;
            right: 20px;
            max-width: 110px;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
            z-index: 30;
            transition: all 0.3s ease;
        }

        .card {
            background-color: #ff4d6d;
            padding: 35px;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
            max-width: 450px;
            width: 90%;
            transition: all 0.3s ease;
            z-index: 10;
            color: white;
        }

        .hidden { display: none !important; }

        .p-principal {
            font-size: 1.6rem;
            font-weight: 700;
            margin-bottom: 15px;
            line-height: 1.3;
        }

        .p-secundario {
            font-size: 1.05rem;
            font-weight: 400;
            opacity: 0.9;
            margin-bottom: 25px;
            line-height: 1.5;
        }

        .btn-container {
            display: flex;
            flex-direction: column;
            gap: 12px;
            justify-content: center;
            align-items: center;
            position: relative;
        }

        .btn-row {
            display: flex;
            gap: 15px;
            width: 100%;
            justify-content: center;
        }

        button {
            padding: 12px 28px;
            border: none;
            border-radius: 25px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            background-color: white;
            color: #ff4d6d;
            transition: transform 0.2s, background-color 0.2s;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        button:hover {
            transform: scale(1.05);
            background-color: #fff0f3;
        }

        .btn-fugiao {
            background-color: #ffe5ec;
            color: #ff4d6d;
            position: relative;
            z-index: 20;
            transition: none;
        }

        input[type="datetime-local"] {
            padding: 12px;
            border: 2px solid white;
            border-radius: 25px;
            margin-bottom: 25px;
            font-size: 1rem;
            color: #ff4d6d;
            background-color: white;
            font-weight: 600;
            outline: none;
            width: 100%;
            text-align: center;
        }
    </style>
</head>
<body>

    <div class="heart-bg" id="heartBg"></div>

    <img src="imagem1.jpg" id="imgTela1" class="topo-direito-img" alt="Foto 1">
    <img src="imagem2.jpg" id="imgTela2" class="topo-direito-img hidden" alt="Foto 2">
    <img src="imagem3.jpg" id="imgTela3" class="topo-direito-img hidden" alt="Foto 3">
    <img src="imagem4.jpg" id="imgTela6" class="topo-direito-img hidden" alt="Foto 4">

    <!-- TELA 1 -->
    <div id="tela1" class="card">
        <p class="p-principal">feliz dia dos namorados, xuxuzinho 🩷</p>
        <div class="btn-container">
            <button onclick="mudarTela('tela1', 'tela2')">vamos lá ✨</button>
        </div>
    </div>

    <!-- TELA 2 -->
    <div id="tela2" class="card hidden">
        <p class="p-principal">hoje é um belo dia e vai ser 2x melhor com você</p>
        <p class="p-secundario">música de fundo: malandro touchscrean 🎵</p>
        <div class="btn-container">
            <div class="btn-row">
                <button onclick="mudarTela('tela2', 'tela3')">Vamos nos encontrar!</button>
                <button class="btn-fugiao" id="btnNao" onmouseover="fugir(this)" onclick="fugir(this)">não</button>
            </div>
        </div>
    </div>

    <!-- TELA 3 -->
    <div id="tela3" class="card hidden">
        <p class="p-principal">sabia que escolheria certo! Você é tão esperto</p>
        <p class="p-secundario">selecione data e hora do encontro após o trabalho 👇🏽</p>
        <input type="datetime-local" id="dataEncontro">
        <div class="btn-container">
            <button onclick="salvarData()">Confirmar data 🗓️</button>
        </div>
    </div>

    <!-- TELA 4 -->
    <div id="tela4" class="card hidden">
        <p class="p-principal">ebaa, te espero igual quiabo rs</p>
        <div class="btn-container">
            <button onclick="mudarTela('tela4', 'tela5')">Escolha de roteiro ☝🏽</button>
        </div>
    </div>

    <!-- TELA 5 -->
    <div id="tela5" class="card hidden">
        <p class="p-principal">O que nós vamos comer?</p>
        <p class="p-secundario">Escolha a sua opção favorita para a nossa noite:</p>
        <div class="btn-container" style="width: 100%;">
            <button style="width: 100%;" class="btn-fugiao" onmouseover="fugir(this)" onclick="fugir(this)">sushi 🍣</button>
            <button style="width: 100%;" class="btn-fugiao" onmouseover="fugir(this)" onclick="fugir(this)">pizza 🍕</button>
            <button style="width: 100%;" class="btn-fugiao" onmouseover="fugir(this)" onclick="fugir(this)">hamborgar 🍔</button>
            <button style="width: 100%;" onclick="escolherRoteiro('Eu + todas as anteriores')">eu + 1 anterior 😈</button>
        </div>
    </div>

    <!-- TELA 6 -->
    <div id="tela6" class="card hidden">
        <p class="p-principal">te amo, nerdddddddddddddd 🩷</p>
        <p class="p-secundario" id="resumoEncontro"></p>
    </div>

    <script>
        const heartBg = document.getElementById('heartBg');
        let totalHearts = 25;
        let speedMultiplier = 1;

        function criarCoracoes() {
            heartBg.innerHTML = '';
            const listHearts = ['🩷', '❤️', '💕', '✨'];
            for (let i = 0; i < totalHearts; i++) {
                const heart = document.createElement('div');
                heart.classList.add('heart-particle');
                heart.innerText = listHearts[Math.floor(Math.random() * listHearts.length)];
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDelay = Math.random() * 5 + 's';
                
                const duration = (Math.random() * 3 + 4) / speedMultiplier;
                heart.style.animationDuration = duration + 's';
                
                heartBg.appendChild(heart);
            }
        }
        
        criarCoracoes();

        function mudarTela(atual, proxima) {
            document.getElementById(atual).classList.add('hidden');
            document.getElementById(proxima).classList.remove('hidden');

            if (proxima === 'tela2') {
                document.getElementById('imgTela1').classList.add('hidden');
                document.getElementById('imgTela2').classList.remove('hidden');
            } else if (proxima === 'tela3') {
                document.getElementById('imgTela2').classList.add('hidden');
                document.getElementById('imgTela3').classList.remove('hidden');
            } else if (proxima === 'tela6') {
                document.getElementById('imgTela3').classList.add('hidden');
                document.getElementById('imgTela6').classList.remove('hidden');
                
                totalHearts = 65;
                speedMultiplier = 2.8; 
                criarCoracoes();
            }
        }

        function fugir(botao) {
            const larguraJanela = window.innerWidth - botao.offsetWidth;
            const alturaJanela = window.innerHeight - botao.offsetHeight;
            
            botao.style.position = 'fixed';
            
            const novoX = Math.random() * (larguraJanela - 40) + 20;
            const novoY = Math.random() * (alturaJanela - 40) + 20;
            
            botao.style.left = novoX + 'px';
            botao.style.top = novoY + 'px';
        }

        let dataSalva = "";
        function salvarData() {
            const inputData = document.getElementById('dataEncontro').value;
            if (!inputData) {
                alert("Escolha o horário para eu me arrumar! 🥰");
                return;
            }
            const dataObjeto = new Date(inputData);
            dataSalva = dataObjeto.toLocaleDateString('pt-BR', {day: '2-digit', month: '2-digit'}) + " às " + dataObjeto.toLocaleTimeString('pt-BR', {hour: '2-digit', minute: '2-digit'}) + "h";
            mudarTela('tela3', 'tela4');
        }

        function escolherRoteiro(opcao) {
            document.getElementById('resumoEncontro').innerHTML = `Nosso encontro está marcado para o dia <b>${dataSalva}</b> com direito a <b>${opcao}</b>!`;
            mudarTela('tela5', 'tela6');
        }
    </script>
</body>
</html>
