---
layout: post
title:  "Wireframes & Mock up, como ser ágil?!"
date:   2016-09-13 18:10:32 -0300
categories: ux
---

![Start Wireframe & Mockup](https://d262ilb51hltx0.cloudfront.net/max/800/1*XOPA8mvLJbtVmO4JgVNLJQ.png)

Quero tratar nesse artigo sobre a viabilidade e a diferença de desenvolver wireframes e como ser ágil para seu projeto, avaliando o tipo de equipe que se encontra mas antes tenho que fazer um breve panorama do porquê disso tudo.

Hoje, conversando com um cliente, tomando nota sobre o que ele deseja que o sistema faça sobre a parte de interface e interações com o usuário, avaliando todos os pontos citados, sabemos que não iremos conseguir coletar todos os requisitos e precisaremos de outras reuniões para fazer com que a aplicação tenha o resultado esperado.

Bom até aí nenhuma novidade, certo? Enquanto o cliente enumera os requisitos, você vaí fazendo um rascunho (papel e caneta) de como acredita que pode ser a interface desse [MVP -  Minimium Viable Product](https://endeavor.org.br/mvp/) e é lógico que o cliente tem pressa.

![Sketch nosso de cada dia!](https://fbcdn-sphotos-e-a.akamaihd.net/hphotos-ak-xlf1/v/t1.0-9/13428421_1198542513503633_4984712604594933393_n.jpg?oh=ce8560e7094eecd5173c5a9e9f47b81d&oe=58774A73&__gda__=1480413160_2725adb6bc0a8c2eddb594580f8340a8)

#### Ferramentas para ser mais Ágil

Sendo assim, já retorno para a estação de trabalho e começo a passar a limpo aqueles rasbicos que fiz e começo a criar um wireframe de "baixa/média-fidelidade", costumo usar o [Caccoo](http://cacoo.com/) como ferramenta de criação de wireframes, existem inúmeras como:

- Axure
- Balsamiq
- MockFlow

 Sobre a minha escolha sobre o Cacoo, alguns pontos relevantes para tomar nota:
 
  - A aplicação é 100% online;
  - Aplicação é "free";
  - Permite compartilhamento do projeto com outras pessoas;
  - Export para PNG (apenas no plano Free);

Com essa gama de recursos que a aplicação me oferece, eu consigo facilmente ser mais assertivo na minha entrega final e qualquer mudança que precisa ser feito durante as próximas reuniões, já posso fazer ao lado do cliente, isso é ser ágil! ;) 

![SancaJobs - Wireframe](https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/e0716442844167.57d99f62c243b.png)

Bem, até aqui falamos de colaboração, refatoração, insigth e feedback, veja que já começamos a tornar o processo que antes era apenas de uma única pessoa a propagar para uma cadeia de fatores e pessoas envolvidas para que o projeto flua de forma mais dinâmica e contínua!

Como nem tudo são flores, já me deparei com equipe que somente o wireframe estático, não é viável, pois a equipe julga alguns pontos importantes, como: 

- Mock navegavél
- Reaproveitamento do HTML & CSS
- Wireframes de alta fidelidade, requerem muita demanda de refatoração até aprovação.

Para este caso, você deve já começar arregaçando as mangas e dando vida para o wireframe, isto é, esqueça os rascunhos crie uma base com os elementos padrões que toda interface vai possuir, como:
 
 - Navegação
 - Botões
 - Tabelas
 - Forms


Dica, recomendo fortemente que nessa etapa, adote um framework CSS para isto:
  - PureCSS
  - [Bootstrap](https://www.getbootstrap.com)
  - Materialize 
  - MDL
   
Enfim estamos falando em ser ágil para a equipe, esses frameworks vão acelerar seu tempo de desenvolvimento e o código será reaproveitado, eles possuem bastante componentes já pronto, não se preocupe com **Cores & Fontes**.

Lembre-se mesmo que esteja validando fluxo, sua principal preocupação deve ser a interação e as ações do usuário. Aqui no [codepen.io](http://codepen.io/cristofersousa/pen/PzBKqJ) eu mostro um rascunho de como fiz a interface e abaixo como ficou o projeto final.

![Mão Aberta - Mock with Bootstrap](https://mir-s3-cdn-cf.behance.net/project_modules/max_1200/7b0e7942844021.57d99e53390d3.jpg)


Para argumentar mais sobre isso, pesquisando sobre UX Design tem esse video  abaixo evidenciando a concepção do processo do UX, e o porquê de wireframes, sobre baixa e alta fidelidade, vale a pena, assite aí!

{% include youtubePlayer.html id="i4Zg6_yKOh8" %}


#### Conclusão

Quando devo fazer wireframe e quanto devo fazer mock? Pela minha experiência, pude observar que deve-se levar em consideração o amadurecimento da equipe e o grau que o projeto já se encontra:

- O projeto já se encontra consolidado e estamos em desenvolvimento? 
- Podemos poupar muito tempo já com o mock, afinal temos basicamente todos os componentes prontos.
 
A então o wireframe seria perca de tempo? Nãoooo! O wireframe serve para os seguintes cenários:

- Validação de fluxos complexo, da qual o cliente está em dúvida ainda qual será a interação do usuário;
- Prévia de validação, ou seja á equipe pode ter uma noção rápida sobre o que está por vir;
- Colaboração, a equipe pode pontuar problemas, ideias e novas formas, naqueles rabisco que tu fez;
- Brainstorm, no momento do wireframe pode coletar vários insigth.

Neste ano ministrei um [Workshop - Do papel a Prototipação](https://speakerdeck.com/cristofersousa/do-papel-a-prototipacao-mobile) no IFSP - Araraquara, na qual demonstro que mesmo com os rascunhos no papel você pode fazer todo fluxo interativo com o usuário e coletar as informações importantes para á aplicação.

Caso você queira testar, para fazer esse workshop, eu utilizei o [POP app](https://popapp.in/) ele basicamente lhe fornece condições para que crie todo o fluxo de interação do aplicativo com o usuário, você tem a possibilidade de tirar fotos do que rascunhou e depois fazendo o mapeamento para as outras telas com isso você pode validar com o cliente, além de ser simples, prático e interativo.

![Prototipando no Papel](https://scontent-gru2-1.xx.fbcdn.net/v/t1.0-9/13103350_1170161953008356_6104476782672874433_n.jpg?oh=2b1ef22df0da1e6c012d749eacf27b00&oe=583FBA22)

Fim!



#### Referencias:
- [Wireframe -  Guia Completo](http://desenvolvimentoparaweb.com/ux/wireframe-web-guia-completo/)
- [Começo do Fim dos wireframes](http://arquiteturadeinformacao.com/user-experience/o-comeco-do-fim-dos-wireframes/)
- [20 Steps to better wireframing ](http://blog.teamtreehouse.com/20-steps-to-better-wireframing)
- [Why prototyping beats wireframing.](https://the-pastry-box-project.net/leisa-reichelt/2012-october-23)
- [Wireframing with pen and paper or on screen?](http://www.sarahevansdesign.co.uk/blog/2016-07-13-wireframing-with-pen-and-paper-or-on-screen)
- [Ferramentas para criação de wireframes](http://desenvolvimentoparaweb.com/ux/ferramentas-criacao-wireframes/)
- [How to get value from wireframes](https://medium.com/@dustin/how-to-get-value-from-wireframes-f40c2cf27960#.bqfelvbp2)
- [Why Prototypes fail in UX Process?](http://www.uxness.in/2015/09/why-prototypes-fail-in-ux-process.html)



