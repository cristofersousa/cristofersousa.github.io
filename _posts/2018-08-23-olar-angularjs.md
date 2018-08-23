--- 
layout: post
title: "AngularJs" 
date: 2018-08-23 01:10:32 -0300 
categories: javascript
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




- Controladores
- Services
- Directives
- Templates
- Filters
