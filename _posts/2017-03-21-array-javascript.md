---
layout: post
title: "Array em JavaScript"
date: 2017-03-21 16:10:32 -0300
categories: web, http,
---

![](http://static4.businessinsider.com/image/564e32c5ecad041068dfb0f1/how-to-win-a-game-of-chess-in-two-moves.jpg)


# Arrays

Quando precisamos trabalhar com conjuntos de valores podemos optar por criar listas.
Em JavaScript listas assim como a maioria das coisas são objetos e possivél armazenar diferentes tipos de valores de uma única vez, associando para essa lista que denominamos de `arrays`.

```
  // declarando um array de forma literal

  console.log(frutas);
  let frutas = ['banana', 'maça', 'pera', 'abacaxi', 'uva','pêssego'];

  ```
Repare que separei o conjunto de itens por `aspas` e `virgulas` pois assim ele entende que esse conjunto de itens se trata de um item exclusivo. Ao adotarmos a propriedade `length` ela retorna o tamanho da nossa lista, isto é, a quantidade de itens que possui no nosso array.

```
  console.log (frutas.length);
  saída > 6
```
Se fizermos:

```

let frutas2 = ['banana, maça, pera, abacaxi, uva, pêssego'];
frutas2.length;

saída > 1
Obs: Veja as aspas! ;)

```

### Manipulação de Array (Push e Pop)

Uma das características interessante sobre arrays é que elas se comportam nativamente como pilhas, bastando então adotarmos o método `push e pop`, para adicionarmos ou removermos um item da nossa lista.

A propriedade `push`:

```
frutas.push('amora');
saída:  amora;

console.log(frutas);
> ['banana', 'maça', 'pera', 'abacaxi', 'uva','pêssego', 'amora'];

```

Removendo itens do Array

A propriedade `pop`:


```
frutas.pop('amora');
saída:  amora;

console.log(frutas);
> ['banana', 'maça', 'pera', 'abacaxi', 'uva','pêssego'];

```

#### Acessando um item do Array

Devemos pensar no seguinte cenário, estamos tratando uma lista de itens e queremos manipular um item dessa lista, sabendo que nossa lista começa a partir do `indice 0`, se quisermos acessar a `fruta: pera`, faríamos:


```
  let frutas = ['banana', 'maça', 'pera', 'abacaxi', 'uva','pêssego'];
  frutas[2];
  > saída: pera

 /* tamanho da string pera */
  frutas[2].length;
  > 4
```


#### Array com tamanho dinâmico

JavaScript com todo seu poder tem uma forma bacana da qual podemos assumir que um array possui um tamanho especifico mas ao inserirmos um novo item ele não gera uma exceção ou exige um tratamento convencional como das outras linguagens para lidar com isso:

```

let names = new Array(10);
names.length;
> 10

names.push('opensanca');
names.length;
> 11

```  

Ou seja haviámos definido um tamanho de 10 posições para o Array, ao dar o `push` adicionamos não somente um elemento, mas sim uma nova posição ao Array, o que indica que tamanhos definidos no construtor servem somente para definir um tamanho inicial e nao um tamanho fixo.


Mas isso pode ser compreendido como um problema, pois se ao declarar um array com 10 posições e ele está vazio o primeiro item ao ser inserido pelo `push` deveria ser da posição **0** e não **11**, isso é o que chamamos de `arrays esparsos`, isso ocorre quando a propriedade length retorna um tamanho que não corresponde à quantidade de elementos dentro de um array.



```
    let names = [];
    names[100] = 'Cristofer';
    names.length;

```
Ou seja os 99 itens do meu array estão vazios somente a 100ª posição está preenchida.

E para finalizar essa sessão de `arrays` vamos falar sobre `Matrizes ou Vetores multidimensionais`, JavaScript não possui uma declaração  especifica para Matrizes e como lidar com isso, conseguimos resolver esse problema com um array de array.

```
var multidimencional = [[1,2,3],[4,5,6],[7,8,9]];
console.log(multidimencional);
```

É isso, dúvida, sugestão ou problema manda aí nos comentários que precisamos melhorar sempre!  ;)

[],s
