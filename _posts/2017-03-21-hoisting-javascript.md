---
layout: post
title: "Hoisting em JavaScript"
date: 2017-03-21 16:10:32 -0300
categories: web, http,
---

# Hoisting

Variáveis podem ser criadas a qualquer momento, múltiplos identificadores  `var` ou `let` podem ser criados dentro do código JavaScript, mas em todas elas o código irá agir como se esta declaraćão tivesse sido feita no inicio da funćão.

Esse comportamento é conhecido como **hoisting** e isso geralmente pode acarretar em problemas de entendimento durante a execućão do seu código, principalmente para quem está vindo de outras linguagens de programaćão.

> Exemplo com var (ES5):

```
  var name = 'Opensanca';

 function sayName() {
   console.log(name);
   var name = 'Opensanca';
 }

 sayName();

```

  Saída obtida: ` name is not defined `


> Exemplo com Let (ES6):

```
 var name = 'Opensanca';

 function sayName() {
   console.log(name);
   let name = 'Opensanca';
 }

 sayName();

```

Saída obtida: ` name is not defined`


Agora entramos no ***Hoisting***, basicamente o que ocorreu para ambos os casos (var e let), mesmo declarando uma variável global a function declarada, "substitui" o que foi passado na ** variável global** por possuir o mesmo nome e com isso temos o resultado  ***undefined***, se você se questionar e por que a function que possui a mesma declaraćão da variavel global, ela não instanciou com o valor definido?

Isso ocorre porque na regra do Hoisting apenas a declaraćão da function será elevada (ićada), sua atribuićão será feita depois do `console.log` o que por sua vez ficará sempre instanciada como `undefined`.

Na íntrega no exemplo que fizemos ele fez o processo abaixo de execućão:

```
var name = 'Opensanca';
function sayName() {
  var name;
  alert(name);
  name = "Opensanca";
}
```

That's all folks
