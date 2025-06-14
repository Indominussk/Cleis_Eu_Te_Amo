<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <title>Para Cleis 💌</title>
  <style>
    body {
      margin: 0;
      padding: 40px 20px 40px 20px;
      background: linear-gradient(to bottom right, #ffd6dc, #ffe9f0);
      font-family: 'Georgia', serif;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
      position: relative;
      color: #4b1a2f;
    }

    /* Container do botão com margem topo maior */
    .botao-container {
      width: 100%;
      display: flex;
      justify-content: center;
      margin: 120px 0 20px 0;
      z-index: 20;
      position: relative;
    }

    .mensagem {
      max-width: 700px;
      background: rgba(255, 255, 255, 0.95);
      padding: 40px 50px;
      border-radius: 16px;
      box-shadow: 0 0 25px rgba(255, 0, 85, 0.25);
      display: none;
      line-height: 1.7;
      font-size: 1.15em;
      text-align: justify;
      position: relative;
      z-index: 20;
    }

    .mensagem p {
      margin-bottom: 1.5em;
    }

    .mensagem h1 {
      color: #d6336c;
      font-size: 2.4em;
      margin-bottom: 0.8em;
      text-align: center;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    button {
      background-color: #ff5c8a;
      color: white;
      border: none;
      border-radius: 12px;
      padding: 14px 28px;
      font-size: 1.2em;
      cursor: pointer;
      transition: background-color 0.3s ease;
      user-select: none;
      position: relative;
      z-index: 20;
    }

    button:hover {
      background-color: #e64973;
    }

    /* Animações base para elementos de amor */
    .animacao {
      position: absolute;
      pointer-events: none;
      z-index: 10;
      user-select: none;
    }

    /* 1) Corações flutuantes */
    .coracao {
      width: 30px;
      height: 30px;
      background-color: #ff4d6d;
      transform: rotate(-45deg);
      animation: flutuar 8s linear infinite;
      opacity: 0.8;
      border-radius: 0;
    }
    .coracao::before,
    .coracao::after {
      content: "";
      position: absolute;
      width: 30px;
      height: 30px;
      background-color: #ff4d6d;
      border-radius: 50%;
    }
    .coracao::before {
      top: -15px;
      left: 0;
    }
    .coracao::after {
      left: 15px;
      top: 0;
    }

    @keyframes flutuar {
      0% {
        transform: translateY(100vh) rotate(-45deg);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(-120vh) rotate(-45deg);
        opacity: 0;
      }
    }

    /* 2) Tulipas subindo */
    .tulipa {
      width: 24px;
      height: 36px;
      background: linear-gradient(45deg, #e4007f 0%, #ff5c8a 100%);
      border-radius: 12px 12px 0 0;
      animation: subirTulipa 10s linear infinite;
      opacity: 0.7;
      filter: drop-shadow(0 0 2px #e4007f);
      position: absolute;
    }
    .tulipa::before {
      content: "";
      position: absolute;
      bottom: -10px;
      left: 50%;
      width: 6px;
      height: 20px;
      background: #3d8758;
      border-radius: 3px;
      transform: translateX(-50%);
    }
    @keyframes subirTulipa {
      0% {
        transform: translateY(110vh);
        opacity: 0;
      }
      50% {
        opacity: 0.8;
      }
      100% {
        transform: translateY(-80vh);
        opacity: 0;
      }
    }

    /* 3) Confetes de coração caindo */
    .confete {
      font-size: 22px;
      color: #ff3366;
      animation: cairConfete 6s linear infinite;
      opacity: 0.9;
      position: absolute;
    }

    @keyframes cairConfete {
      0% {
        transform: translateY(-10vh) rotate(0deg);
        opacity: 0;
      }
      50% {
        opacity: 1;
      }
      100% {
        transform: translateY(110vh) rotate(360deg);
        opacity: 0;
      }
    }

    /* Corações que aparecem ao clicar */
    .popup-coracao {
      position: absolute;
      font-size: 24px;
      animation: subir 1s ease-out forwards;
      color: red;
      pointer-events: none;
      z-index: 30;
      user-select: none;
    }

    @keyframes subir {
      0% {
        transform: translateY(0);
        opacity: 1;
      }
      100% {
        transform: translateY(-50px);
        opacity: 0;
      }
    }
  </style>
</head>
<body onclick="criarCoracao(event)">

  <div class="botao-container">
    <button onclick="mostrarMensagem()">Clique para ver minha declaração 💖</button>
  </div>

  <article class="mensagem" id="mensagem" role="main" aria-label="Declaração para Cleis">
    <h1>Para você, Cleis 💖</h1>
    <p>Nestes 5 meses ao seu lado, eu descobri um amor que vai muito além do que eu poderia imaginar.</p>
    <p>Foram dias incríveis, cheios de carinho, risos, aprendizados e momentos que guardo no coração com muito cuidado. Cada instante contigo é especial — e estar com você é uma das melhores escolhas da minha vida.</p>
    <p>Você é linda em todos os sentidos. Seu jeito estudioso, determinado, o quanto você se empenha nas coisas que faz, tudo isso só aumenta a minha admiração por você.</p>
    <p>E além de tudo, você é carinhosa, amorosa, doce… Um presente que Deus colocou no meu caminho.</p>
    <p>Cleis, você é muito mais do que minha namorada. Você é minha paz, meu orgulho, meu motivo de sorrir.</p>
    <p>Quero você na minha vida pra sempre. Te amo muito. Mas tipo... muito mesmo. Mais do que palavras conseguem explicar.</p>
    <p>Com todo meu amor,<br>Thiago 💘</p>

    <button onclick="dizerTeAmo()">Te amo ❤️</button>
  </article>

  <!-- Animações ao fundo -->
  <script>
    function random(min, max) {
      return Math.random() * (max - min) + min;
    }

    function criarAnimacoes() {
      const body = document.body;
      const larguraTela = window.innerWidth;

      // Corações flutuantes
      for (let i = 0; i < 10; i++) {
        const coracao = document.createElement("div");
        coracao.className = "coracao animacao";
        coracao.style.left = random(0, larguraTela) + "px";
        coracao.style.animationDelay = random(0, 8) + "s";
        coracao.style.animationDuration = random(6, 10) + "s";
        body.appendChild(coracao);
      }

      // Tulipas subindo
      for (let i = 0; i < 8; i++) {
        const tulipa = document.createElement("div");
        tulipa.className = "tulipa animacao";
        tulipa.style.left = random(0, larguraTela) + "px";
        tulipa.style.animationDelay = random(0, 10) + "s";
        tulipa.style.animationDuration = random(8, 12) + "s";
        body.appendChild(tulipa);
      }

      // Confetes de coração caindo
      for (let i = 0; i < 15; i++) {
        const confete = document.createElement("div");
        confete.className = "confete animacao";
        confete.style.left = random(0, larguraTela) + "px";
        confete.style.animationDelay = random(0, 6) + "s";
        confete.style.animationDuration = random(5, 7) + "s";
        confete.textContent = "💘";
        body.appendChild(confete);
      }
    }

    window.onload = criarAnimacoes;

    // Mostrar a mensagem e esconder botão
    function mostrarMensagem(event) {
      document.getElementById('mensagem').style.display = 'block';
      event.target.style.display = 'none';
    }

    // Alerta "Te amo"
    function dizerTeAmo() {
      alert('Te amo muito, Cleis! ❤️');
    }

    // Criar coração ao clicar (efeito extra fofo)
    function criarCoracao(e) {
      const cora = document.createElement('div');
      cora.classList.add('popup-coracao');
      cora.innerText = '❤️';
      cora.style.left = `${e.clientX}px`;
      cora.style.top = `${e.clientY}px`;
      document.body.appendChild(cora);
      setTimeout(() => cora.remove(), 1000);
    }
  </script>
</body>
</html>
