--- 
layout: post
title: "Olar, AngularJs" 
date: 2018-09-27 22:10:32 -0300 
categories: javascript, angularjs, controllerAs, binding
---

![](https://portswigger.net/cms/images/70/b8/6d8685eb222c-article-xss-without-html-client-side-template-injection-angularjs-article.png)

Olar, pessoas, tudo certo?
Bora fazer uma série sobre AngularJS, atualmente estou lidando com manutenção do monolito aqui na ContaAzul, na qual a stack atual é AngularJS versão 1.3.

Eu já tinha trabalhado com [Ember](https://emberjs.com/) na [SHX](http://www.shx.com.br/site/) e [Vue](https://vuejs.org/) na [CasaeCafe.com](https://app.casaecafe.com/), até então um projeto com o famoso AngularJS ainda não havia pego de unhas e dentes, apenas havia tido um contato bem "hello world".

Bahhhh, estamos em 2018 e você trabalhando com AngularJS na [ContaAzul](https://app.contaazul.com/), pois é, e posso ser sincero contigo, estou adorando isto, estou vendo o porquê de algumas abordagens que os frameworks JavaScript mais atuais adotaram a partir do AngularJS e os ajustes que foram feito para não cair no mesmo problema que o AngularJs apresentou.

Atualmente, estou no time que está fazendo a frente de um módulo de gestão contábil, da qual estou começando a adotar o conceito de [microfrontends](https://micro-frontends.org/) pois pretendo fazer a migração para Vue, como nosso produto possui centenas de usúarios acessando, essa migração deve ser feita com cautela, o minimo de impacto para o cliente e grande valor para o desenvolvimento e para nossa stack, então a dica de inicio é, enxergue a oportunidade.  Como tenho que dar  manutenção em cima do monolito, essa stack basicamente se compoẽ das seguintes tecnologias:
 
 - ES5 
 - Less
 - Gulp
 - AngularJs v.13
 - Jasmine e Karma
 - Bootstrap 3
 - algumas libs marotas (RequireJs e Lodash) 

Estarei criando um post logo em seguida abordando sobre ás similiaridades entre VueJs e AngularJs e como podemos fazer a migração com `microfrontends` para dentro de um monolito sem estourar o timebox da equipe, que é minha tese na pós-graduação da [UFSCar](http://latosensu.dc.ufscar.br/desenvolvimento-de-software-para-web-2018/).

Mas antes disso, gostaria de abordar alguns pontos que acho de vital importância para quem pretende dar uma sobrevida com projetos que ainda estão com AngularJS em sua stack e como não cair em algumas armadilhas, durante o desenvolvimento.


### O Velho Mundo e o Novo Mundo

Bom, não é novidade que AngularJS morreu, alguns problemas foram detectados no seu core e acharam melhor reescrever o framework com uma abordagem diferente, já que até então React estava vindo com força com o conceito de `Virtual DOM` e Vue meio que inespressivo, estava começando a tomar forma.  
 
Porém, não podemos cuspir no prato que comemos, AngularJS teve uma enorme importância no universo web e a mudança de chave para o que conhecemos de client-side hoje, devemos isso á este framework. Antes dele até possuíamos Ember e Backbone mas era bastante inexpressivo, somente com a chegada do AngularJS e um padrinho forte Google(lógico).

Logo, com esse desfecho é natural que vamos encontrar diversos produtos de grandes empresas, ainda, adotando essa tecnologia,  como [Azul Empresas Aéreas](https://www.voeazul.com.br/). 

Sabendo disso precisamos dar um "refresco" na memória de quem está chegando agora e vai trabalhar com AngularJS, porque ele foi importante? O que ele fez de tão "tchan" para engenharia web, que eu denomino como `velho mundo` e depois como `novo mundo`.

Acredito que seja importante sabermos isso, para entender para onde a web caminhou e está caminhando. Simplesmente esbravejar na sua mesa sobre poxa essa empresa ainda usa essa stack velha, mas vamos compreender o porquê delas ainda possuírem em seu core esse framework.

### Sobre arquitetura 

AngularJS tem uma arquiteura MVC (Model View Controller) / MVVM (Model-View-ViewModel), a sua principal filosofia nesse contexto é separar as unidades lógicas e responsabildiades no desenvolvimento de aplicações, pense em camadas quando for pensar em MVC. 

Hoje quando ouvimos isso, pensamos em [webcomponent](https://www.webcomponents.org/introduction), mas para época ainda não poderia ser dito isso, mesmo depois com a evolução do framework, breve resumo quando ouvir sobre MVC no AngularJS.

 - `Model:` Modelo, corresponde aos dados por trás da aplicação, geralmente acessados pelo servidor.
 - `Controller:` Controlador, corresponde a lógica/regra de negócios.
 - `View:` Visão, corresponde à nossa  UI (user interface), a parte que nosso usuário interage.

`MVVM`: Como o controlador é responsável por decidir, basicamente, que partes do modelo devem ser exibidas na visão,
de acordo com a implementação, ele também poderá ser considerado como uma `viewmodel` daí o modelo MVVM, por isso o 
two way data binding.

![Architecture MVC AngularJS](https://image.slidesharecdn.com/aevolucaodoangularjs-150517123511-lva1-app6892/95/a-evoluo-do-angularjs-46-638.jpg?cb=1431866296)

Tem até um artigo abordando, problemas falhos em adotar o conceito de MVC no front-end, se trata do [Detecting Inconsistencies in JavaScript MVC Applications](https://ieeexplore.ieee.org/document/7194585)

### Check Point 

Bem, antes de sair criando nossas Directives, Controllers, Services gostaria de entrar em alguns contextos que são relevantes para você que está chegando de mala e cuia no AngularJS.

> $scope vs controllerAs
Por que devemos deixar de usar o $scope? A partir da versão AngularJS 1.2 foi introduzido o controllerAs, motivo disso?
Ele permite a definição  de variáveis na instância do controlador usando a palavra-chave `this` e fazer referência a estas variaveis por meio do controlador a partir do HTML.

Precisamos fazer um "memorando" sobre o `this`, leia-se Escopo.

O this: é o `sudo` em JavaScript, ao invoca-lo você está dizendo necessariamente que uma função pode ser sobreescrita por qualquer função que seja chamada, além de que o this dentro e fora de uma função pode se referir a dois objetos ou escopos totalmente diferentes. Pensa na bagunça que isso pode virar um exemplo simples dois controladores que tragicamente possuem dois modelos (carro e pessoa) e necessariamente o desenvolvedor colocou `name` para a variavel delas, o que vai rolar, com isso? I N S A N I D A D E! 

Por isso para que o escopo não se perca, recomenda-se como boa prática não adotar o $scope, use uma variavel proxy, no caso o [John Papa](https://johnpapa.net/angularjss-controller-as-and-the-vm-variable/) - usa no lugar de proxy a variavel vm, aqui nos projetos estou adotando `$ctrl`, faz mais sentido pois o desenvolvedor que olhar na view, aquele `ng-model=" $ctrl.name"`, já saberá que estou me referindo ao controller.
 
Caso queira saber mais sobre Escopo e Hoisting, tem esse [artigo](https://medium.com/opensanca/hoisting-em-javascript-9f22b1f78448)!

###  ng-bind vs ` { { double mustache } } `

A vatangem do ng-bind em relação a {{ }} (mustaches duplos) é que o AngularJS consometempo para inicializar e executar até que ele possa encontrar e substituir todas as chaves duplas do HTML. Isso, significa que durante alguns instante em que o naveador é iniciado, você poderá ver chaves duplas aparecendo na UI até que o AngularJS  tenha a oportunidade de entrar em ação e substituí-las. Isso ocorre somente na primeira carga da página, e não em visões carregadas posteriormente.

### O que vamos ver ainda nessa série:

- Controladores
- Services
- Directives
- Templates
- Filters
- Factories

Até mais.. ;) 

