---
title: IA e BoardGames
date: '2021-03-01'
tags:
  - boardgames
  - compsci
  - PT
---

Após várias partidas de boardgames e aulas de ciências da computação, não pude evitar de traçar certas conexões entre estes dois mundos. Mais notoriamente, eu acho, foi o jeito que a teoria básica sobre inteligência artificial e a experiência de jogar jogos estão relacionados.

Como este texto supõe que o leitor já está familiarizado com boardgames além de War e Monopoly, mas não necessariamente com algoritmos, primeiramente vamos ver um pouco de background sobre IA.

Há séculos atrás, já haviam artistas e alquimistas sonhando em como o mundo seria se seres arquitetados por humanos conseguissem perceber e interagir com o mundo a sua volta de maneira inteligente. Mas há apenas algumas décadas cientistas modernos se empenharam na tarefa de fazer isto acontecer. Dentre os passos necessários, está a pergunta: "o que é inteligência?" "o que é agir de forma inteligente?"

Para o propósito de criar esse ser, a definição matemática cunhada foi: "um agente inteligente é uma entidade que percebe o mundo através de sensores, tem um conjunto de ações que consegue fazer, e escolhe como agir de maneira a maximizar os seus ganhos de acordo com uma função de utilidade. Podendo usar de seus conhecimentos, aprendizado sequencial ou apenas reflexos." [1]

![Figura representando um diagrama de um agente inteligente que percebe o ambiente com sensores e age sobre ele com atuadores](/images/bg_ia_1.png "Figura retirada do livro [1]")


Creio que com isso já podemos perceber uma grande semelhança entre um agente inteligente e um jogador de boardgame. Pois é exatamente isso que fazemos em um jogo. Observamos o ambiente do tabuleiro e das peças e agimos de maneira a maximizar nossos pontos, basicamente, no mundo dos jogos, somos convidados a agir de acordo com a definição formal de inteligência citada acima de uma maneira bem direta e clara. A teoria da Inteligência artificial traz definições muito interessantes para tipos diferentes de agentes e ambientes. Aliás, vou escrever "jogador" ao invés de "agente" e "tabuleiro" ao invés de "ambiente" neste texto a partir de agora.

Os tabuleiros podem ser dos seguintes tipos:

- Acessível vs. Inacessível: digamos que um tabuleiro é acessível se nenhuma parte crucial está escondida do agente. Um jogo de xadrez é um tabuleiro acessível. Um jogo de pôquer é inacessível, pois as cartas dos oponentes não são observáveis.
- Determinístico vs. Estocástico: Um tabuleiro determinístico é aquele que o próximo estado depende apenas das escolhas feitas pelo jogador. Um tabuleiro estocástico é onde aleatoriedade pode interferir no resultado. Ou seja: Tem dado rolando na mesa ou não tem?
- Estático vs. Dinâmico: Um tabuleiro dinâmico é um que pode mudar de repente enquanto o jogador está pensando sobre o que fazer. Jogos em tempo real são dinâmicos. A maioria dos jogos turn-based são ambientes estáticos.
- Episódico vs. Não Episódico: Um tabuleiro episódico é aquele que escolhas passadas não interferem em nada na estratégia. Você não precisa se lembrar do que fez ou planejar o que fará daqui a cinco rodadas. Consegue prosseguir apenas observando o estado atual do jogo, enquanto o não episódico requer uma memória sobre as jogadas passadas.
- Discreto vs. Contínuo: Um tabuleiro discreto é um em que cada ação te desloca em unidades inteiras. Por exemplo, um tabuleiro quadriculado, em que uma ação possível é "mova 2 casas". Em um tabuleiro contínuo não existe isso. Jogos como X-Wing que usam régua para movimentar agem em tabuleiro contínuo.

Jogadores podem ser dos seguintes tipos, do menos para o mais complexo:

- Movido a Reflexos: Este jogador geralmente está em um jogo episódico e dinâmico. Um carro autônomo está em uma estrada dinâmica e quando ver um obstáculo precisa se desviar. Um jogador de Dobble precisa encontrar o match entre as cartas e pegá-las imediatamente. Em nenhum desses casos existe opções complexas e decisão difícil.
- Movido a Modelos: O jogador movido a modelos vive em um tabuleiro inacessível. Ele precisa fazer uma estimativa mental sobre como é a parte inacessível para poder navegar o mais eficientemente possível e atingir seu objetivo.
- Movido a Objetivos: este jogador irá fazer o que for preciso e estiver a seu alcance para alcançar seu objetivo fixo.
- Função de Utilidade: Aqui, o jogador possui uma função interna que dita o que ele irá fazer. Ele sempre fará a ação que lhe deixará mais "feliz" de acordo com esta função. Há vários caminhos possíveis para chegar ao objetivo e também pode haver vários estados de vitória e este agente escolhe o que mais gosta.
- Aprendizado: Aí entramos na tecnologia de ponta. Um jogador desse tipo é voltado ao auto melhoramento. Possui um "crítico" interno e um "ator" externo, o crítico é quem vai definir se ele atingiu seu objetivo ou não, e o "ator" irá escolher ações diferentes em partidas futuras para ver se assim consegue melhorar sua performance aos olhos do crítico. [2] Este agente é o mais poderoso de todos e pode lidar com as situações mais complexas.

Se olharmos acontecimentos importantes da história da computação, vemos que jogos de tabuleiro sempre tiveram muito a ver com IA. Não é à tôa que os primeiros supercomputadores dedicados à inteligência artificial, como o DeepBlue e o Watson, foram testados contra humanos em partidas de jogos de Xadrez ou Go. Pois estes são jogos que ocorrem no ambiente mais simples possível. Determinístico, estático, acessível, discreto, episódico.

A tradução de uma pessoa real para uma inteligência artificial é tão direta no mundo dos jogos, que até existe um sistema chamado Solo System [3], que é um modelo de um "jogador extra" que pode ser utilizado em qualquer jogo, caso faltem amigos para jogar, da mesma maneira que vários jogos de tabuleiro também possuem adversários autômatos em versões online. O Solo System de certo modo simplificado externaliza o que está se passando na cabeça de um jogador "função de utilidade" com suas cartas de personalidade e mantém o ambiente como sendo estocástico pela imprevisibilidae das ações, já que tem também cartas para confirmar se o "adversário invisível" vai ou não jogar do jeito que quem o está controlando imaginou.

<aside>
👉 Referências: 
[1] - Artificial Intelligence - A Modern Approach (Stuart J. Russell and Peter Norvig)
[2] - https://en.wikipedia.org/wiki/Intelligent_agent
[3] - https://boardgamegeek.com/boardgame/206074/solo-system

</aside>