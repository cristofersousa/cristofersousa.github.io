---
layout: post
title:  "Hello JavaScript aka ES6!"
date:   2016-09-09 18:10:32 -0300
categories: javascript, node
---

![]http://wallpapersdsc.net/wp-content/uploads/2015/11/414.jpg)

Hello JavaScript, ou ES6/JavaScript2015, essa semana começamos um novo treinamento aqui no [Opensanca](www.opensanca.com.br) que chamamos de Trilha Developer, o foco desse treinamento e disponibilizar uma carga horária mais extensa com encontros semanais (terça e quinta das 19:30 ás 22:30), dissecando uma tecnologia do básico até o avançado. No semestre passado oferecemos um treinamento de Python -  [Trilha de Python](https://github.com/opensanca/trilha-python) com 60h de treinamento que foi cuidadosamente passada com os conhecimentos do [Luiz Menezes](https://github.com/lamenezes).  E agora começamos com a [Trilha Developer - Full Stack JavaScript](https://github.com/opensanca/trilha-javascript).

Bom, e aqui estou eu para começar essa nova saga de documentar o que aprendo nesta trilha, vamos ver os seguintes tópicos:

- JavaScript Básico com ES6
- JavaScript DOM/BOM com ES6
- Node
- Angular
- MondoDB
- Ember
- React & Flux
- Ionic 1
- Testes Unitários

Então, vamos lá, fique livre para comentar e argumentar sobre os artigos aqui postados sobre a linguagem, com certeza toda discussão é válida, hoje vamos começar instalando o Node.js e o nosso primeiro Hello World! Vamos lá, então! \o/

### Ambiente

Bom, para você começar um treinamento de JavaScript, no modo "antigo", antes você precisava apenas:
  - Browser
  - Notepad (editor de texto)

Certo, de um tempo para cá, bastante coisa mudou, surgiu o [Node - JavaScript no servidor](www.nodejs.org), editores de texto para web com mais recursos para codar, debug e afins.  Enfim, estamos em tempos áureos para Web ainda mais com JavaScript!  

Sabemos que cada [Browser](http://www.html5rocks.com/pt/tutorials/internals/howbrowserswork/) tem sua particularidade e  sendo assim, vamos ignorar neste começo o browser, vamos usar o Node para compilar nossos arquivos JS ao invés de usar o Browser para isso! Okay!? ;)

Então vamos lá, o que você precisará:

- [Atom -  editor de texto](www.atom.io)
- [Node.js](www.nodejs.org)

### Instalação

Instalando nosso editor de texto, Atom! Estamos escolhendo o Atom, pois ele é opensource, existe uma infinidade de recursos, plugins e macetes que nos auxiliará durante nosso desenvolvimento e amadurecimento da linguagem JavaScript, então,  bora lá!

##### Atom

** Plataforma Windows / Mac **

  > 1. Instale o Atom (next, next e finish)

** Plataforma Linux/Mac **

  > 1. sudo add-apt-repository ppa:webupd8team/atom
  > 2. sudo apt-get update
  > 3. sudo apt-get install atom

##### Node

Instalando o Node, por enquanto vamos começar com o processo de introdução ao JavaScript, mas depois quando entrar na parte web, vamos precisar de um servidor rodando, mais um motivo positivo para iniciar com ele! ;)

** Plataforma Windows / Mac **

   > 1. Instale o Node (next, next e finish)


** Plataforma Linux/Mac **

> 1. curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -

> 2. sudo apt-get install -y nodejs

##### Controle de versão para Node

E se eu quiser trabalhar com várias versões do NODE? Hoje a versão atual é v6.5.0 mas vamos supor que estou em algum projeto que a equipe estava adotando a v4.5.0, afinal não seria problema pois a comunidade do Node oferece suporte para as versões antigas por até 20 anos! ;)

Bom, e quem vamos usar nesse caso? Vamos usar uma lib que chama-se [N](https://github.com/mklement0/n-install), ela funciona para Linux/Mac, usuários da plataforma Windows devem adotar o [NVM ](http://nomadev.com.br/node-js-o-que-%C3%A9-nvm-e-como-gerenciar-vers%C3%B5es-do-node/).

** Plataforma Linux/Mac **

Cheque a versão do Node que você no momento na sua máquina instalada:

/* versão do node*/

> node -v

Depois de checar pode instalar outra veersão do node, antes instale o N:

> sudo npm install -g n

Agora, basta inserir o comando:

> sudo n latest

Pronto seu node, estará com a versão mais recente!

** Plataforma Windows **
> 1. Instalar o [NVM](https://github.com/coreybutler/nvm-windows)
> 2. next, next e finish

#### Testando nosso ambiente

Bom, daqui para frente seguirei apenas com a plataforma Mac/Linux que é terminal, pessoas do Windows é so abrir o terminal(prompt de comando)  de vocês e seguir o processo!

Chegou a hora do famoso, Hello World, abra o terminal e execute o código:

> -  node
- console.log('Hello World!');
-  Hello World!

Fim!
