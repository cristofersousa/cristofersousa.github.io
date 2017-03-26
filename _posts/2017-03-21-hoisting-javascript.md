---
layout: post
title: "Hoisting em JavaScript"
date: 2017-03-21 16:10:32 -0300
categories: javascript
---

![](http://legosse.com.br/lego/image/cache/data/LEGO_BRICK_MORE/10663_4-640x640.jpg)


Antes de entrarmos em Hoisting precisamos entender o que é o **Escopo** em JavaScript, basicamente o escopo de uma variável é a região do código-fonte  de seu programa em que ela está definida. Uma variável global tem escopo global, esta por sua vez fica definida em toda parte de seu código JavaScript, ou seja pode ser chamada a qualquer momento.

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

**Dica:** Embora seja possível não utilizar a instrução **var ou let** ao escrever código no escopo global, var ou let sempre dever ser usada para declarar variáveis locais, se você não fizer isso ocorrerá o seguinte:

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

Algumas linguagens de programação semelhantes ao C, a cada bloco de código declarado dentro de chaves:

```
 function {  
   // seu código aqui
 }
```

 Possui seu escopo próprio e as variáveis não são visivéis fora do bloco de declaração, ou seja de suas funções.
 No JavaScript isso é chamado de **escopo de bloco** e JavaScript não possui esse conceito, isso causa muita dor de cabeça para desenvolvedores que estão iniciando em JavaScript.

Como alternativa a isto o JavaScript possui **escopo de função**, onde as variáveis são visíveis dentro da função em que são definidas e dentro  de qualquer função independente do seu aninhamento, exemplo:


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
O escopo de função em JavaScript significa que todas as variáveis declaradas dentro de uma função são visíveis por todo o corpo da função. Curiosamente, isso significa que as variáveis são visíveis mesmo antes de serem declaradas. Essa característica é informalmente conhecida no cenário JavaScript como **Hoisting**, o código JavaScript nesse cenário se comporta como se todas as declarações de variável em uma função fossem "içadas/elevadas" para o topo da função.

### Hoisting

Vimos anteriormente que Hoisting ocorre por conta do escopo de função, variáveis podem ser criadas a qualquer momento, múltiplos identificadores `var` ou `let` podem ser criados dentro do código JavaScript, mas em todas elas o código irá agir como se esta declaração tivesse sido feita no inicio da função, causando o içamento.

Exemplo com **var**:

```
  var name = 'Opensanca';

 function sayName() {
   console.log(name);
   var name = 'Opensanca';
 }

 sayName();

```

  > Saída obtida: name is not defined


Exemplo com **let**:

```
 let name = 'Opensanca';

 function sayName() {
   console.log(name);
   let name = 'Opensanca';
 }

 sayName();

```

> Saída obtida: name is not defined


Reforçando, com os exemplos acima, entramos no cenário ***Hoisting***, basicamente o que ocorreu para ambos os casos (var e let), mesmo declarando uma variável global a function declarada, "substitui" o que foi passado na ** variável global** por possuir variáveis de mesmo nome e com isso temos o resultado ***undefined***, se você se questionar e por que a function que possui a mesma declaração da variável global, ela não instanciou o valor definido?

Isso ocorre porque na regra do Hoisting apenas a declaração da function será elevada (içada), sua atribuição será feita depois do `console.log` o que por sua vez ficará sempre instanciada como `undefined`, lembre-se JavaScript possui **escopo de função**.

Na íntrega no exemplo que fizemos a engine do JavaScritpt fez o seguinte procedimento com a nossa declaração:

```
let name = 'Opensanca';       // nossa variável global
  function sayName() {
    let name;                // nossa variável local de mesmo nome que a global
    console.log(name);       // chamando a variável local dentro da function
    let = "Opensanca";       // nossa variavel global foi para dentro da function pois ocorreu o hoisting e com isso não temos nenhuma atribuição global para o JS o que resulta em `undefined`
}
```

Concluimos com isso, evite esse problema declararando todas as variáveis que necessita na primeira linha, a fim de evitar duplicidade de nomes em relação a uma variável que foi declarada posteriormente, pois assim não irá ocorrer esquecimento ou confusão sobre o resultado esperado sobre alguma function.

That's all folks! 
