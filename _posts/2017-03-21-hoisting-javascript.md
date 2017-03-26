---
layout: post
title: "Hoisting em JavaScript"
date: 2017-03-21 16:10:32 -0300
categories: javascript
---

![](http://maxroecker.github.io/blog/javascript-intermediario-3/hoist.svg)


Antes de entrarmos em Hoisting precisamos entender o que é o **Escopo**, basicamente o escopo de uma variável é a região do código-fonte  de seu programa em que ela está definida. Uma variável global tem escopo global, esta por sua vez fica definida em toda prte de seu código JavaScript, ou seja pode ser chamada a qualquer momento.

Por outro lado, as variáveis declaradas dentro de uma função estão definidas somente dentro do corpo da funçãa, esta por sua vez funciona apenas dentro do corpo de uma função ou seja localmente. Os parâmetros de função gtambém contam como variáveis locais e estão definidos somente dentro do corpo da função.

Porém agora vem a dúvida da maioria dos programadores iniciantes em JavaScript, uma função com variável local possui precedência sobre uma variável global com o mesmo nome, isto é uma variável global perde sua **"identidade"**, basicamente então temos se declararmos uma variável local ou um parâmetro de função com o mesmo nome de uma variávelglobal, ela efetivamente oculta a variável global.

```
  let scope = "global"      // declara uma variável global
  function checkscope() {   
    let scope = "local";    // declara uma variável local com o mesmo nome da global
    return scope;           
  }

  checkscope();
  > saída: "local"

```

**Dica:** Embora seja possível não utilizar a instrução **var ou let** ao escrever código no escopo global, var ou let sempre dever ser usada para declarar variáveis locais.
Se você não fizer isso ocorre o seguinte:

```
  scope = "global";              // declara uma variável global mesmo sem var

  function checkscope2() {
    scope = "local";             // alterando o valor da variável global pela local
    myScope = "local";           // adicionando uma nova variável global mesmo dentro da função

    return  [scope, myScope];     // retornando os dois valores declarados dentro da function
  }

  checkscope2();                 // ["local", "local"]: temos efeitos colaterais aqui, esperavamos **["global, local"]**

```

### Escopo de função

Algumas linguagens de programação semelhantes ao C, cada bloco de código dentro de chaves tem seu escopo próprio e as variáveis não são visivéis fora do bloco de declaração, ou seja de suas funções. No JavaScript isso é chamado de **escopo de bloco** e JavaScript não possui esse conceito, isso causa muita dor de cabeça para desenvolvedores que estão iniciando em JavaScript.

Como alternativa a isto o JavaScript possui **escopo de função**, onde as variáveis são visíveis dentro da função em que são definidas e dentro  de qualquer função que esteja aninhada dentro dessa função.


```
  function test(o) {
    var i = 0;      // i está definida para toda a função
    if (typeof o == "object") {
      var j= 0;

        for (var k=0; k <=10; k++) {
          console.log(k);
        }
        console.log(k);
    }
    console.log(j);
  }

```
O escopo de função em JavaScript significa que todas as variáveis declaradas dentro de uma função são visíveis por todo o corpo da função. Curiosamente, isso significa que as variáveis são visíveis mesmo antes de serem declaradas. Essa característica é informalmente conhecida no cenário JavaScript como **Hoisting**, o código JavaScript se comporta como se todas as declarações de variável em uma função ( mas não em qualquer atribuição associada) fossem "içadas/elevadas" para o topo da função.

### Hoisting

Variáveis podem ser criadas a qualquer momento, múltiplos identificadores `var` ou `let` podem ser criados dentro do código JavaScript, mas em todas elas o código irá agir como se esta declaração tivesse sido feita no inicio da função.

Esse comportamento é conhecido como **hoisting** e isso geralmente pode acarretar em problemas de entendimento durante a execução do seu código, principalmente para quem está vindo de outras linguagens de programação, hoisting traduzindo para o português é "içamento/elevar", ou seja vou pegar um item e eleva-lo sobre as outras coisas, mas que coisas?

> Exemplo com var (ES5):

```
  var name = 'Opensanca';

 function sayName() {
   console.log(name);
   var name = 'Opensanca';
 }

 sayName();

```

  > Saída obtida: name is not defined


> Exemplo com Let (ES6):

```
 var name = 'Opensanca';

 function sayName() {
   console.log(name);
   let name = 'Opensanca';
 }

 sayName();

```

> Saída obtida: name is not defined


Com os exemplos acima, entramos no famoso cenário ***Hoisting***, basicamente o que ocorreu para ambos os casos (var e let), mesmo declarando uma variável global a function declarada, "substitui" o que foi passado na ** variável global** por possuir variáveis de mesmo nome e com isso temos o resultado  ***undefined***, se você se questionar e por que a function que possui a mesma declaração da variável global, ela não instanciou o valor definido?

Isso ocorre porque na regra do Hoisting apenas a declaração da function será elevada (içada), sua atribuição será feita depois do `console.log` o que por sua vez ficará sempre instanciada como `undefined`.

Na íntrega no exemplo que fizemos ele fez o processo abaixo durante a sua execução:

```
var name = 'Opensanca';
function sayName() {
  var name;
  alert(name);
  name = "Opensanca";
}
```
That's all folks! 
