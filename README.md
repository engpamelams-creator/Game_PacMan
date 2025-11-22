# Pac-Man — Game_pacman

Resumo
- Jogo Pac-Man em HTML5 Canvas com lógica em JavaScript.
- Estrutura pensada para rodar localmente no navegador (servido por Live Server ou um HTTP server simples).

Arquivos principais
- `pacman.html` — marcação, canvas, controles e footer com link para Dev Pamela M.S.
- `style.css` — tema visual estilo arcade (CRT / neon); responsivo.
- `pacman.js` — classe Pacman: movimentação, colisões, animação e desenho.
- `ghost.js` — classe Ghost: IA básica (BFS para direção), movimento, colisões e desenho.
- `ui.js` — UI e controle do loop (DOMContentLoaded): start/restart, score, lives, highscore, responsividade do canvas.
- `game.js` — loop do jogo, atualização global, criação de objetos, lógica de pontuação/vidas.
- Assets: `animations.gif`, `ghost.png` (sprites usados por pacmanFrames / ghostFrames).

Como executar (Windows / VS Code)
1. Abra o projeto no VS Code na pasta:
   `C:\Users\Pamela Menezes\Desktop\Game_pacman`
2. Servir os arquivos:
   - Recomendado: extensão Live Server → abrir `pacman.html` e clicar "Go Live".
   - Ou via terminal integrado:
     - Python: `py -m http.server 8000` → abra `http://localhost:8000/pacman.html`
     - npx: `npx http-server -p 8000`
3. Abra DevTools (F12) → Console para ver erros / logs.

Notas importantes (ajustes e boas práticas aplicadas)
- Scripts carregados com `defer` e inicialização dentro de `DOMContentLoaded` para evitar execução antes do DOM.
- `highScore` é tratado como número (parseInt) antes de usar/armazenar no localStorage.
- `pacman.js`: uso de Math.floor para índices de mapa e correções de rotação/ânulo para renderizar o sprite corretamente.
- `ghost.js`: correção na função addNeighbors (verificação correta de linhas/colunas) para evitar caminhos inválidos.
- `ui.js` expõe funções globais úteis: `updateScore`, `updateLives`, `updateHighScore`, `endGameUI`.
- Canvas é mantido responsivo visualmente; o buffer do jogo ainda usa a resolução interna do script (ajustável).

Como debugar erros comuns
- Erro 404: verifique se os assets (`animations.gif`, `ghost.png`) existem na raiz do projeto.
- ReferenceError / TypeError: abra console (F12) e veja a linha indicada — normalmente é devido a ordem de carregamento dos scripts ou nomes globais faltando.
- Se o loop rodar antes da inicialização: confirme `defer` nos scripts e inicialização em `DOMContentLoaded`.

Como modificar
- Mapa do jogo: editar a matriz `originalMap` (provavelmente em `game.js`).
- Velocidade/frames: ajustar `fps`, `oneBlockSize`, e `speed` nas classes.
- Sprites: substituir `animations.gif` / `ghost.png` mantendo tamanho de bloco (`oneBlockSize`).

Licença / Créditos
- Projeto de treino / exemplo — ajuste livre para uso pessoal ou aprendizado.

Desenvolvido por "Dev Pamela M.S"