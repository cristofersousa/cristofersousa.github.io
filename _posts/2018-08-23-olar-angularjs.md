--- 
layout: post
title: "AngularJs" 
date: 2018-08-23 01:10:32 -0300 
categories: javascript, angularjs, controllerAs, binding
---

# Olar, AngularJS!?

![](https://portswigger.net/cms/images/70/b8/6d8685eb222c-article-xss-without-html-client-side-template-injection-angularjs-article.png)

### Overview

Faz um certo tempo que não escrevo, malz, me tornei pai e troquei de empresa em 2017 e a vida ficou bem corrida.
De quebra comecei 2018, dando um salto na carreira decidi sair da minha zona de conforto e vim morar em Santa Catarina (Joinville), 
rolou um "invite" pela ContaAzul em meados de Dezembro/2017, mas deixa isso para outro post, o que posso dizer agora sobre é se tiver
interesse em saber mais sobre a ContaAzul, manda um [ping](cristofer.sousa@gmail.com).


### AngularJS / Legado 

Bem, como nem tudo são flores estou trabalhando atualmente com manutenção em um monolito/legado que temos o AngularJS versão 1.3. =O
Eu já tinha trabalhado com Ember e Vue mas nunca tinha pego um projeto com AngularJS então a experiência está sendo bem bacana, estou até para documentar as similiaridades entre VueJs e AngularJs e como podemos fazer a migração com `microfrontends`.

Mas antes disso, vou abordar alguns pontos que acho de vital importância para quem tem que dar mais uma "bomba de oxigênio" para o produto.

### Velho Mundo / Novo Mundo

Bom, não é novidade que AngularJS morreu, alguns problemas foram detectados no seu core e acharam melhor reescrever o framework com uma abordagem diferente, já que até então React estava vindo com força com o conceito de `Virtual DOM` e Vue meio que inespressivo, estava começando a tomar forma.  
 
Porém, não podemos cuspir no prato que comemos, AngularJS teve uma enorme importância no universo web e a mudança de chave para o que conhecemos de Web hoje, temos graças a este framework. Antes deles até possuiamos Ember, Backbone mas eles não possuiam uma adesão tão grande como foi o AngularJS.

Logo, com esse desfecho é natural que vamos encontrar diversos produtos de grandes empresas, ainda, adotando essa tecnologia, dica inspeciona o site da empresa aérea [Azul](https://www.voeazul.com.br/). 

Sabendo disso precisamos dar um "refresco" na memória de quem está chegando agora e de quem já passou pelo AngularJS, porque ele foi importante? O que ele fez de tão "tchan" para engenharia web, antes denominada de "velho mundo" e depois como "novo mundo", disso vamos entender o por que dos frameworks mais atuais serem similares e quais dores eles tentam cobrir e evitar com o histórico do AngularJs.

### Arquitetura

AngularJS tem uma arquiteura MVC (Model View Controller) ou MVVM (Model-View-ViewModel), a sua principal filosofia nesse contexto 
é separar as unidades lógicas e responsabildiades no desenvolvimento de aplicações. Hoje quando ouvimos isso, pensamos logo em `webcomponent`, mas para época ainda não poderia ser dito isso, então em míudos seria:

 - Model: Modelo, corresponde aos dados por trás da aplicação, geralmente acessados pelo servidor.
 - Controller: Controlador, corresponde a lógica/regra de negócios.
 - View: Visão, corresponde à nossa  UI (user interface), a parte que nosso usuário interage.

`MVVM`: Como o controlador é responsável por decidir, basicamente, que partes do modelo devem ser exibidas na visão,
de acordo com a implementação, ele também poderá ser considerado como uma `viewmodel` daí o modelo MVVM, por isso o 
two way data binding.

### Pontos fortes: 

> $scope vs controllerAs
Por que devemos deixar de usar o $scope? A partir da versão AngularJS 1.2 foi introduzido o controllerAs, motivo disso?
Ele permite a definição  de variáveis na instância do controlador usando a palavra-chave `this` e fazer referência a estas variaveis por meio do controlador a partir do HTML.

Precisamos fazer um "memorando" sobre o `this`.

O this: é o `sudo` em JavaScript, ao invoca-lo você está dizendo necessariamente que uma função pode ser sobreescrita por qualquer função que seja chamada, além de que o this dentro e fora de uma função pode se referir a dois objetos ou escopos totalmente diferentes. Pensa na bagunça que isso pode virar um exemplo simples dois controladores que tragicamente possuem dois modelos (carro e pessoa) e necessariamente o desenvolvedor colocou `name` para a variavel delas, o que vai rolar, com isso? I N S A N I D A D E! 

Por isso para que o escopo não se perca, recomenda-se como boa prática não adotar o $scope, use uma variavel proxy, no caso o [John Papa](https://johnpapa.net/angularjss-controller-as-and-the-vm-variable/) - usa no lugar de proxy a variavel vm, aqui nos projetos estou adotando `$ctrl`, faz mais sentido pois o desenvolvedor que olhar na view, aquele `ng-model=" $ctrl.name"`, já saberá que estou me referindo ao controller.
 
Caso queira saber mais sobre Escopo e Hoisting, tem esse [artigo](https://medium.com/opensanca/hoisting-em-javascript-9f22b1f78448)!

> ng-bind vs {{ }}

A vatangem do ng-bind em relação a {{ }} (mustaches duplos) é que o AngularJS consometempo para inicializar e executar até que ele possa encontrar e substituir todas as chaves duplas do HTML. Isso, significa que durante alguns instante em que o naveador é iniciado, você poderá ver chaves duplas aparecendo na UI até que o AngularJS  tenha a oportunidade de entrar em ação e substituí-las. Isso ocorre somente na primeira carga da página, e não em visões carregadas posteriormente.


- Controladores
- Services
- Directives
- Templates
- Filters
