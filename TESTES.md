# Validação da versão entregue

Testes automatizados em Microsoft Edge / Chromium sem interface visível, abrindo o HTML local. Acesso à rede bloqueado durante a verificação offline.

## Resultados

- Inicialização do menu e início de partida: passou.
- Queda da primeira peça: 16 cm confirmados somente após assentamento.
- Rotação por teclado e botões: passou.
- Arraste por eventos de toque: moveu a peça e manteve o estado de posicionamento ao soltar o dedo.
- Soltar por botão e clique de mouse: passou.
- Pausa, continuação e reinício com limpeza da pontuação e das peças: passaram.
- Queda fora da base: encerrou a partida sem contar altura em queda.
- Recorde após recarregar a página: preservado.
- Armazenamento local indisponível: jogo iniciou, assentou uma peça e pontuou sem erro.
- Alternância do som e criação do áudio: sem erro de execução; não houve avaliação auditiva humana.
- Inspeção das capturas de tela em 1440 × 960, 390 × 844 e 844 × 390. Layout em paisagem corrigido após inspeção.
- Zero erros JavaScript e zero requisições HTTP/HTTPS na rodada de regressão offline.
- Teste de torre com sequência controlada de quadrados: 12 peças confirmadas, 192 cm, corpos em repouso, próxima peça disponível. A sequência fixa foi usada apenas no teste; a versão entregue sorteia as formas.
- Testes isolados da física para as sete formas em quatro orientações: verificados separadamente sobre a plataforma.

## Limites

O toque foi simulado em navegador; não houve teste em aparelhos físicos Android/iOS nem em Safari/Firefox. O ZIP está preparado para hospedagem estática, mas não foi publicado em uma conta GitHub. Os testes não garantem estabilidade de qualquer empilhamento: escorregar, girar e derrubar a torre fazem parte da dinâmica. O teste de 12 quadrados verifica a estabilidade numérica de uma pilha regular, não todas as combinações possíveis.

## Atualização: giro por gesto vertical

O gesto de celular foi restaurado: mantendo o dedo na tela, movimentos horizontais posicionam a peça e movimentos verticais giram em passos de 90° a cada 45 pixels. Para cima gira à esquerda; para baixo, à direita. Os botões continuam disponíveis e tirar o dedo não dispara a queda.

Teste automatizado dos manipuladores reais de eventos, executados em ambiente simulado: movimento e giro simultâneos, limiar de 45 pixels, pequenos movimentos sem giro acidental, inversão de sentido, vários giros no mesmo toque, segundo dedo ignorado, fim do toque sem queda, comportamento do mouse preservado e bloqueio durante a queda. Todos passaram. Esta atualização não foi testada em aparelho físico.
