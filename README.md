
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Mentor Virtual Inclusivo</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap');

    :root {
      --color-primary: #314ee1; /* Cor primária */
      --color-secondary: #8c77f5; /* Cor secundária */
      --color-accent: #422ec1; /* Cor de acento */
      --color-bg: #ffffff; /* Cor de fundo */
      --color-text: #000000; /* Cor do texto */
      --border-radius: 14px;
      --shadow-soft: 0 8px 24px rgba(139, 111, 240, 0.3);
      --transition-speed: 0.4s;
      --max-width: 900px;
    }
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Nunito', sans-serif;
      background: linear-gradient(135deg, var(--color-primary) 20%, var(--color-secondary) 60%);
      color: var(--color-text);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: flex-start;
      padding: 2rem 1rem;
    }
    main {
      background: var(--color-bg);
      border-radius: var(--border-radius);
      box-shadow: var(--shadow-soft);
      width: 100%;
      max-width: var(--max-width);
      display: flex;
      flex-wrap: wrap;
      overflow: hidden;
    }
    header {
      width: 100%;
      background: var(--color-primary);
      padding: 2rem 2.5rem;
      color: white;
      border-top-left-radius: var(--border-radius);
      border-top-right-radius: var(--border-radius);
      box-shadow: inset 0 -4px 10px rgba(0,0,0,0.15);
      font-family: 'Montaser Arabic', cursive;
      user-select: none;
    }
    header h1 {
      margin: 0;
      font-weight: 700;
      font-size: 2.8rem;
      letter-spacing: 0.04em;
      text-shadow: 0 0 10px rgba(139,111,240,0.7);
    }
    header p {
      margin-top: 0.4rem;
      font-weight: 500;
      font-size: 1.1rem;
      color: var(--color-accent);
      max-width: 600px;
      font-family: 'Nunito', sans-serif;
      user-select: none;
    }
    section.form-section {
      flex: 2 1 500px;
      padding: 2rem 3rem 2rem 3rem;
      background: var(--color-bg);
      display: flex;
      flex-direction: column;
      gap: 1.8rem;
      font-family: 'Nunito', sans-serif;
    }
    form label {
      font-weight: 600;
      font-size: 1.1rem;
      margin-bottom: 0.3rem;
      user-select: none;
    }
    select, textarea, input[type="text"] {
      border-radius: var(--border-radius);
      border: 2px solid var(--color-primary);
      font-size: 1rem;
      padding: 14px 18px;
      width: 100%;
      transition: border-color var(--transition-speed);
      font-family: inherit;
      resize: vertical;
      box-shadow: inset 0 3px 10px var(--color-accent);
    }
    select:focus, textarea:focus, input[type="text"]:focus {
      outline: none;
      border-color: var(--color-secondary);
      box-shadow: 0 0 10px var(--color-secondary);
    }
    textarea {
      min-height: 120px;
      line-height: 1.5;
    }
    button {
      background: var(--color-primary);
      color: var(--color-bg);
      font-weight: 700;
      font-size: 1.35rem;
      border: none;
      border-radius: var(--border-radius);
      padding: 16px 0;
      cursor: pointer;
      box-shadow: 0 8px 16px rgba(139,111,240,0.7);
      transition: background-color var(--transition-speed), box-shadow var(--transition-speed);
      user-select: none;
      font-family: 'Nunito', sans-serif;
    }
    button:hover,
    button:focus {
      background: var(--color-secondary);
      box-shadow: 0 10px 30px rgba(136,226,235,0.85);
      outline: none;
    }

    section.chat-section {
      flex: 1 1 350px;
      background: var(--color-accent);
      border-top-right-radius: var(--border-radius);
      border-bottom-right-radius: var(--border-radius);
      box-shadow: inset 0 0 15px rgba(255, 255, 255, 0.4);
      display: flex;
      flex-direction: column;
      padding: 2rem 1.8rem;
      max-height: 620px;
      overflow: hidden;
      position: relative;
      font-family: 'Nunito', sans-serif;
    }
    #chat {
      flex-grow: 1;
      overflow-y: auto;
      padding-right: 1rem;
      scrollbar-width: thin;
      scrollbar-color: var(--color-primary) transparent;
    }
    #chat::-webkit-scrollbar {
      width: 8px;
    }
    #chat::-webkit-scrollbar-track {
      background: transparent;
    }
    #chat::-webkit-scrollbar-thumb {
      background-color: var(--color-primary);
      border-radius: 20px;
    }
    .message {
      max-width: 80%;
      margin-bottom: 1.25rem;
      padding: 12px 18px;
      border-radius: var(--border-radius);
      box-shadow: 0 4px 12px rgba(0,0,0,0.12);
      font-size: 1rem;
      line-height: 1.4;
      user-select: text;
      word-wrap: break-word;
    }
    .mentor {
      background: var(--color-primary);
      color: var(--color-bg);
      align-self: flex-start;
      border-radius: var(--border-radius)  var(--border-radius)  var(--border-radius)  0;
      text-shadow: 0 1px 2px rgba(0,0,0,0.15);
      filter: drop-shadow(0 1px 0 rgba(0,0,0,0.15));
      animation: fadeInUp 0.5s ease forwards;
    }
    .user {
      background: var(--color-secondary);
      color: var(--color-text);
      align-self: flex-end;
      border-radius: var(--border-radius)  var(--border-radius)  0 var(--border-radius);
      font-weight: 600;
      animation: fadeInUp 0.4s ease forwards;
    }
    #points {
      font-weight: 700;
      color: var(--color-primary);
      font-size: 1.3rem;
      margin-top: 1rem;
      user-select: none;
      text-align: center;
      letter-spacing: 0.02em;
    }
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translate3d(0, 8px, 0);
      }
      to {
        opacity: 1;
        transform: none;
      }
    }
    @media (max-width: 900px) {
      main {
        flex-direction: column;
        max-width: 600px;
      }
      section.chat-section {
        order: -1;
        border-radius: var(--border-radius) var(--border-radius) 0 0;
        max-height: 350px;
        padding-bottom: 1rem;
      }
      section.form-section {
        padding: 1.5rem 1.5rem 2rem 1.5rem;
      }
    }
    /* Screen reader only */
    .sr-only {
      position: absolute;
      width: 1px;
      height: 1px;
      margin: -1px;
      padding: 0;
      border: 0;
      overflow: hidden;
      clip: rect(0 0 0 0);
      clip-path: inset(50%);
      white-space: nowrap;
      user-select: none;
    }
  </style>
</head>
<body>
  <main>
    <header>
      <h1>Mentor Virtual Inclusivo</h1>
      <p>Seu assistente pessoal para aprender melhor e cuidar do seu bem-estar.</p>
    </header>
    <section class="form-section" aria-label="Formulário para obter ajuda do mentor virtual">
      <form id="mentorForm" autocomplete="off">
        <label for="difficulty">Qual sua maior dificuldade de estudo atualmente?</label>
        <select id="difficulty" required aria-required="true" aria-describedby="difficultyHelp" >
          <option value="" disabled selected>Selecione</option>
          <option value="organizacao">Organização e planejamento</option>
          <option value="foco">Manter o foco</option>
          <option value="conteudo">Compreender o conteúdo</option>
          <option value="ansiedade">Ansiedade ou estresse</option>
          <option value="outro">Outro</option>
        </select>
        <div id="difficultyHelp" class="sr-only">Escolha a maior dificuldade que você está enfrentando nos estudos.</div>

        <label for="feeling">Como você está se sentindo hoje?</label>
        <select id="feeling" required aria-required="true" aria-describedby="feelingHelp">
          <option value="" disabled selected>Selecione</option>
          <option value="motivado">Motivado e confiante</option>
          <option value="cansado">Cansado ou desmotivado</option>
          <option value="ansioso">Ansioso ou preocupado</option>
          <option value="feliz">Feliz e animado</option>
          <option value="triste">Triste ou desanimado</option>
        </select>
        <div id="feelingHelp" class="sr-only">Informe qual é seu estado emocional atual.</div>

        <label for="goal">Qual seu objetivo principal nos estudos?</label>
        <select id="goal" required aria-required="true" aria-describedby="goalHelp">
          <option value="" disabled selected>Selecione</option>
          <option value="melhorar_notas">Melhorar as notas</option>
          <option value="concluir_tarefas">Concluir tarefas a tempo</option>
          <option value="reduzir_ansiedade">Reduzir ansiedade</option>
          <option value="aprender_mais">Aprender mais</option>
          <option value="outro">Outro</option>
        </select>
        <div id="goalHelp" class="sr-only">Escolha o principal objetivo que deseja alcançar com seus estudos.</div>

        <button type="submit" aria-label="Enviar dados para o mentor virtual">Pedir ajuda ao Mentor</button>
      </form>
      <div id="points" aria-live="polite" aria-atomic="true">Pontos: 0</div>
    </section>

    <section class="chat-section" aria-label="Chat entre o usuário e o mentor virtual" role="log" aria-live="polite" aria-relevant="additions">
      <div id="chat" tabindex="0" aria-live="polite" aria-atomic="false" >
        <div class="message mentor" tabindex="-1">Olá! Estou aqui para ajudar você a aprender melhor e se sentir bem. Por favor, responda ao formulário ao lado para que eu possa te orientar.</div>
      </div>
    </section>
  </main>

  <script>
    const form = document.getElementById('mentorForm');
    const chat = document.getElementById('chat');
    const pointsDisplay = document.getElementById('points');

    let points = 0;

    const suggestions = {
      organizacao: [
        "Faça uma lista diária de tarefas para organizar seu dia.",
        "Divida seus estudos em blocos de 25 minutos com pequenas pausas (Técnica Pomodoro).",
        "Use uma agenda ou app para controlar prazos e provas."
      ],
      foco: [
        "Desligue as notificações do celular enquanto estuda.",
        "Encontre um local tranquilo e livre de distrações.",
        "Estabeleça pequenas metas para cada sessão de estudo."
      ],
      conteudo: [
        "Tente explicar o conteúdo para alguém, isso ajuda a fixar o que aprendeu.",
        "Utilize vídeos e animações para facilitar a compreensão.",
        "Não tenha medo de perguntar aos professores ou colegas quando algo não estiver claro."
      ],
      ansiedade: [
        "Pratique técnicas de respiração profunda para aliviar o estresse.",
        "Reserve momentos para atividades que te relaxem, como caminhada ou música.",
        "Lembre-se que sentir ansiedade é normal, e pedir ajuda é um ato de coragem."
      ],
      motivado: [
        "Aproveite essa energia para avançar nos estudos e revisar conteúdos.",
        "Estabeleça desafios para manter a motivação sempre alta.",
        "Compartilhe seu entusiasmo com colegas para criar uma rede de apoio."
      ],
      cansado: [
        "Tente dedicar alguns minutos ao descanso para renovar as energias.",
        "Durma bem, pois o sono é fundamental para o aprendizado.",
        "Organize seus estudos para evitar sobrecarga."
      ],
      ansioso: [
        "Identifique os gatilhos da sua ansiedade e converse com alguém sobre eles.",
        "Pratique exercícios físicos para liberar tensões.",
        "Considere técnicas de meditação para acalmar a mente."
      ],
      feliz: [
        "Use essa disposição para ajudar colegas e trocar conhecimentos.",
        "Refletir sobre suas conquistas fortalece a confiança.",
        "Mantenha hábitos que promovam sua felicidade."
      ],
      triste: [
        "Procure conversar com alguém de confiança sobre seus sentimentos.",
        "Não se cobre demais, todos temos dias difíceis.",
        "Atividades físicas e contato com a natureza podem ajudar."
      ],
      melhorar_notas: [
        "Estabeleça uma rotina de estudos focada nas matérias com mais dificuldade.",
        "Faça resumos e revise com frequência.",
        "Peça feedback aos professores para saber onde melhorar."
      ],
      concluir_tarefas: [
        "Priorize as tarefas mais urgentes e que exigem mais esforço.",
        "Divida os trabalhos grandes em etapas menores para facilitar o progresso.",
        "Evite deixar para o último momento."
      ],
      reduzir_ansiedade: [
        "Incorpore pausas regulares durante o estudo para evitar sobrecarga.",
        "Use técnicas de mindfulness para relaxar a mente.",
        "Fale com profissionais caso a ansiedade esteja muito intensa."
      ],
      aprender_mais: [
        "Explore conteúdos complementares para expandir seu conhecimento.",
        "Participe de grupos de estudo para trocar experiências.",
        "Pratique exercícios para fixar o conteúdo."
      ]
    };

    function addMessage(text, sender = 'mentor') {
      const div = document.createElement('div');
      div.classList.add('message', sender);
      div.textContent = text;
      div.setAttribute('tabindex', '-1');
      chat.appendChild(div);
      chat.scrollTop = chat.scrollHeight;
      div.focus();
    }

    function chooseSuggestions(category) {
      let key = category.toLowerCase().replace(/\s/g, '_');
      if (suggestions[key]) {
        return suggestions[key];
      }
      return ["Continue perseverando! Estou aqui para ajudar no que precisar."];
    }

    form.addEventListener('submit', e => {
      e.preventDefault();

      const difficulty = form.difficulty.value;
      const feeling = form.feeling.value;
      const goal = form.goal.value;

      if (!difficulty || !feeling || !goal) {
        alert('Por favor, preencha todas as respostas.');
        return;
      }

      addMessage(`Minha dificuldade: ${form.difficulty.options[form.difficulty.selectedIndex].text}`, 'user');
      addMessage(`Como estou me sentindo: ${form.feeling.options[form.feeling.selectedIndex].text}`, 'user');
      addMessage(`Meu objetivo principal: ${form.goal.options[form.goal.selectedIndex].text}`, 'user');

      const difficultyAdvice = chooseSuggestions(difficulty);
      const feelingAdvice = chooseSuggestions(feeling);
      const goalAdvice = chooseSuggestions(goal);

      function respondSequentially(messages, index = 0) {
        if (index >= messages.length) return;
        setTimeout(() => {
          addMessage(messages[index]);
          points++;
          pointsDisplay.textContent = `Pontos: ${points}`;
          respondSequentially(messages, index + 1);
        }, 1500);
      }

      addMessage("Analisando suas respostas...", 'mentor');

      setTimeout(() => {
        addMessage("Aqui vão algumas sugestões para sua dificuldade:", 'mentor');
        respondSequentially(difficultyAdvice);

        setTimeout(() => {
          addMessage("Agora, algumas dicas para seu estado emocional:", 'mentor');
          respondSequentially(feelingAdvice);

          setTimeout(() => {
            addMessage("Por fim, para alcançar seu objetivo:", 'mentor');
            respondSequentially(goalAdvice);
          }, (feelingAdvice.length + 1) * 1600);
        }, (difficultyAdvice.length + 1) * 1600);
      }, 1500);

      form.reset();
      form.difficulty.focus();
    });
  </script>
</body>
</html>
```
