# TrabalhoPratico1TDVJ
Repositório do Trabalho Pratico 01 - Tecnicas De Desenvolvimento de Videojogos - 18816(José Oliveira) & 25955(David Cruz)

Este SpaceShooter é um jogo (de 1 até 2 jogadores) no qual o jogador controla uma nave espacial. O objetivo do jogo é que o jogador consiga o máximo de score enquanto viaja no espaço sem perder todas as suas vidas. No espaço, irá encarar diversos obstáculos, naves inimigas que dificultaram a missão do jogador. Em seu favor, o jogador terá acesso a uma metralhadora que poderá usar em sua defesa.

Explicação do código:

Program.cs: Vai ser este código que permite o programa correr o jogo.

Component.cs: Uma classe que chama os componentes do jogo e atualiza-os ao longo do decorrer do jogo. Draw() server para desenhar os componentes. Update() é utilizado para atualizar o tempo do jogo.

Game1.cs: Uma classe publica, que irá, primeiramente, definir um valor random, introduzir os valores da dimensão da tela, e criar estados de jogo.

Initialize(): Ao iniciar o jogo, a tela vai assumir os valores pretendidos e vai fazer com que o rato estaja visível.

LoadContent(): Quando o jogo carregar, um menu irá aparecer as seguintes opções: "1 player", "2 players", "highscores" e "quit".

UnloadContent(): Será chamado de vez em quando para remover componentes desnecessários do jogo.

Pasta Content 

Contem todos os assets necessários para o funcionamento do jogo.

Pasta Controls 

Button.cs: Classe que controla os botões do jogo. Define o tamanho, a posição, o texto e a aparencia dos mesmos.

Pasta Managers 

AnimationManager.cs: Classe que tem como objetivo o de todas as animações do jogo. Tem métodos que desenham, atualizam, iniciam e param animações.

EnemyManager.cs: É responsável pelo controlo dos inimigos. Tem propriedades que definem o valor máximo de inimigos, o tempo entre o spawn de inimigos e a quantidade de projéteis que eles lançam contra o jogador. Tem também métodos para atualizar e adicionar novos inimigos.

ScoreManager.cs: Classe que possui métodos para guardar, carregar e atualizar novas pontuações alcançadas pelo jogador. Carrega também os top 10 melhores pontuações guardadas num ficheiro XML.

Pasta Models

 Animations.cs: Classe que implementa um ICloneable interface e tem propriedades para o frame atual, contagem de frames, altura de frames, velocidade de frames, largura de frames, looping e textura. Possui também um método de clonar.

Input.cs: Representa os inputs para o jogador utilizar para mover e disparar. Cima, Baixo, Esquerda, Direita e Disparar.

Score.cs: Classe que contem duas propriedades, uma para introduzir o nome do jogador e outra para introduzir a pontuação do mesmo.

Pasta Sprites 
Bullet.cs: Classe que tem as propriedades das balas que o jogador e o inimigo disparam. Contem valores da velocidade e duração da bala. Tem também um metodo para controlar a colisão com outros sprites.

Enemy.cs: Subclasse da classe Ship e representa as naves inimigas. Esta classe dá Override ao Update() e ao OnCollide() para introduzir comportamentos para os inimigos.

Explosion.cs: Subclasse da classe Sprite e representa a animação de explosão. Possui um timer que determina quando a animação termina e a explosão é removida.

ICollidable.cs: Controla as colisões entre objetos no jogo.

Player.cs: Subclasse da classe Ship e representa a nave do jogador. A class controla os controlos, movimento, disparos, deteção de colisões e vida do jogador.

Ship.cs: Subclasse da classe Sprite e implementa ICollidable. Tem propriedades de vida e de balas, como também um campo de velocidade. Possui um Constructer que pega num objeto Texture2D e um shoot() que cria uma nova bala e adiciona a uma lista de herdados. Possui também um OnCollide() que retorna uma NotImplementedException.

Sprite.cs: Esta Classe server para controlar os sprites do jogo, quanto à sua textura, posição, rotação ou escala.

Pasta States 

GameState.cs: Subclasse da Classe State e representa o estado do jogo. Contem uma lista de sprites, incluindo jogadores e inimigos e controla os seus updates, colisões e remoções. Controla também o desenho de sprites e no display de informação acerca do jogador.
HighscoreState.cs: Mostra a pontuação máxima de jogadores no jogo. Carrega essa informação a partir de um ficheiro XML e carrega-os na tela.

MenuState.cs: Subclasse da Classe State e representa o menu principal do jogo. Contem uma lista de botões e uma imagem de fundo. Cada botão altera o estado de jogo.

State.cs: Classe abstrata que server como classe base para os diferentes estados do jogo. Possui 4 métodos: LoadContent, Update, PostUpdate, and Draw. Tem também dois campos protegidos: _game (instância da classe Game1) e _content (instancia da classe ContentManager).
