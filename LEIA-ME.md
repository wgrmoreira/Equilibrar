# Equilíbrio! — Um pouco mais alto

Empilhe peças sobre uma pequena plataforma e alcance a maior altura estável.

## Jogar

Abra **index.html** em um navegador moderno. Não é necessário instalar nada, iniciar servidor ou ter conexão com a internet. O arquivo contém o jogo, os estilos, o motor de física, a arte e os sons.

## Controles

| Ação | Computador | Celular / tablet |
| --- | --- | --- |
| Mover | Mouse, ← → ou A / D | Arrastar na área de jogo ou botões ← → |
| Girar | Q / E, ↑, roda do mouse ou ↶ ↷ | Arrastar o dedo para cima/baixo ou botões ↶ ↷ |
| Soltar | Clique na área de jogo, espaço, Enter, ↓ ou botão Soltar | Botão Soltar |
| Pausar / continuar | P, Esc ou botão Ⅱ | Botão Ⅱ e Continuar |
| Reiniciar | Pausa → Recomeçar a partida | Pausa → Recomeçar a partida |
| Som | Botão ♪ / ♫ | Botão ♪ / ♫ |

No celular, arraste horizontalmente para mover e verticalmente para girar, mantendo o mesmo toque. Cada 45 pixels verticais giram a peça em 90°: para cima, à esquerda; para baixo, à direita. Os movimentos podem ser combinados. Tirar o dedo da tela não solta a peça: o botão Soltar evita quedas acidentais. O som começa desligado; ative-o no cabeçalho durante a partida.

## Regras

- A projeção tracejada indica onde acontece o primeiro contato vertical. A peça ainda pode girar ou escorregar depois do impacto.
- Toda a torre precisa ficar praticamente imóvel por 1 segundo e conectada à plataforma para confirmar uma peça e registrar altura.
- A medida é a maior altura confirmada na partida; peças em queda não contam. A escala do jogo usa 4 unidades de desenho por centímetro.
- Quando uma peça cai abaixo da plataforma, a partida termina. Não há limite de tempo para posicionar ou esperar a torre assentar.
- As sete formas são sorteadas em sacos embaralhados. A primeira peça é quadrada para facilitar o início.
- A câmera se adapta à altura e ao tamanho da tela. Redimensionar a janela não muda a geometria do mundo.
- A partida pausa automaticamente ao trocar de aba ou perder o foco.

## Recorde

O navegador salva o recorde e a preferência de som localmente. A chave `equilibrio_record` preserva compatibilidade com o jogo original quando ambos usam a mesma origem. Dados de um arquivo aberto no computador não são transferidos automaticamente para o endereço publicado. Em navegação privada ou com armazenamento bloqueado, o jogo continua funcionando, mas a persistência pode ficar indisponível.

## GitHub Pages

1. Coloque **index.html** na raiz do repositório.
2. Nas configurações do repositório, abra **Pages** e selecione publicação pela branch desejada, usando a pasta raiz.
3. Abra o endereço fornecido pelo GitHub após a publicação.

Não há etapa de compilação, caminhos absolutos, arquivos auxiliares obrigatórios, CDN, fontes remotas, telemetria ou chamadas de rede. Em um site publicado, o primeiro acesso precisa baixar a página; para jogar sem conexão, salve ou baixe o HTML e abra-o localmente. Não há service worker ou instalação de PWA.

## Implementação

Canvas 2D, JavaScript e CSS. Física com Matter.js 0.20.0 incorporado ao HTML, incluindo sua licença MIT. As colisões usam retângulos unidos rigidamente e mesclados onde possível para reduzir emendas e oscilações. Simulação em passos fixos de 120 Hz, atrito, amortecimento, repouso de corpos e verificação geométrica de apoio. As peças permanecem corpos físicos; confirmar uma peça não a transforma em uma plataforma fixa.

Arte desenhada com Canvas/CSS; sons sintetizados com Web Audio. Há suporte a teclado, foco visível, mensagens de estado e preferência por movimento reduzido. O jogo depende de informação visual e não oferece navegação espacial completa para leitores de tela.

Veja **TESTES.md** para o escopo da validação.
