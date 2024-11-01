<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Juan 💖</title>
    <style>
        /* Estilos básicos para o corpo */
        body, html {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #ffccff, #ccffff);
            overflow: hidden;
        }

        /* Pergunta centralizada e decorada */
        #question {
            font-size: 1.8em;
            text-align: center;
            color: #ff69b4;
            cursor: pointer;
            background: rgba(255, 255, 255, 0.8);
            padding: 20px;
            border-radius: 15px;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
        }

        /* Contêiner escondido para a imagem e o botão */
        #response {
            display: none;
            text-align: center;
            margin-top: 20px;
        }

        /* Estilo para o botão */
        #yesButton {
            padding: 10px 20px;
            font-size: 1.4em;
            color: #fff;
            background-color: #ff69b4;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
        }

        /* Imagem da garota */
        .chica {
            width: 150px;
            margin-top: 10px;
            display: block;
        }

        /* Efeito final do botão */
        .hearts {
            font-size: 1.5em;
            background: linear-gradient(90deg, #ff69b4, #ffb6c1);
            color: #fff;
        }
    </style>
</head>
<body>

    <!-- Pergunta inicial -->
    <div id="question">(⁠◕⁠ᴗ⁠◕⁠✿⁠)Juan🌸💗 ¿Tú quieres estar comigo en todas las aventuras para siempre?🌈💖♡o⁠(⁠( ⁠^⁠▽⁠^ )⁠)⁠o💖</div>

    <!-- Resposta que aparece após clicar na pergunta -->
    <div id="response">
        <img src="https://example.com/chica.png" alt="Chica" class="chica">
        <button id="yesButton">Sí💗</button>
    </div>

    <script>
        // Variáveis de controle
        const question = document.getElementById('question');
        const response = document.getElementById('response');
        const yesButton = document.getElementById('yesButton');
        let clickCount = 0;

        // Exibe a resposta ao clicar na pergunta
        question.addEventListener('click', () => {
            question.style.display = 'none';
            response.style.display = 'block';
        });

        // Lógica para o botão "sí" se mover
        yesButton.addEventListener('mouseover', () => {
            if (clickCount < 8) { // Número de vezes que o botão foge
                const x = Math.random() * (window.innerWidth - yesButton.clientWidth);
                const y = Math.random() * (window.innerHeight - yesButton.clientHeight);
                yesButton.style.position = 'absolute';
                yesButton.style.left = `${x}px`;
                yesButton.style.top = `${y}px`;
                clickCount++;
            } else {
                // Após algumas tentativas, transforma o botão
                yesButton.classList.add('hearts');
                yesButton.innerHTML = "💖💗💘💝💖";
                yesButton.style.cursor = 'default';
                yesButton.removeEventListener('mouseover', arguments.callee);
            }
        });
    </script>

</body>
</html>
