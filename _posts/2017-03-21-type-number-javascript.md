---
layout: post
title: "O tipo Number em JavaScript"
date: 2017-03-21 16:10:32 -0300
categories: web, http,
---

Em JavaScript `number` sempre serão pontos flutuantes  independente da forma como você declara eles seja inteiro.
Vamos nos basear no exemplo a seguir, para isso vamos usar o **===** que compara tipo e valor:

```
if(1 === 1.0) {
  console.log(1 === 1.0);
}
 saída > isso resulta em uma operação verdadeira,  e além do mais os dois valores são iguais além de ser do tipo `number`.  
```

Agora vamos comparar um tipo `number` com um tipo `string`, porém agora temos que usar apenas **==** pois serão tipos diferentes e resultarão em false se comparar os tipos.

```
  let numero = 1;
  let string = "1";

  if (numero == string) {
    console.log ('verdade');
  } else {
    console.log ('falso');
  }

  saída >  verdade

```
# NAN (Not a Number)

`NaN` é um erro que ocorre sempre que se espera por um número, e acabamos por receber outros valores, apesar de JavaScript não usar tipagem estática, dentro do motor de processamento de sua engine ele sabe examente como lidar com isto, e acaba disparando essa exceção.

```
 console.log(Number('123'));
 saída > undefined
 ```
Por que no exemplo acima ele gerou `undefined`?

```
 console.log(Number('teste'));
 saída > NaN

```
 Ele tenta ler um tipo `String` como `Number` e gera a exceção.
 
### Conclusão

Simples né, praticamente entender que todo número em JavaScript é convertido para um tipo ***float*** e existe o ***NaN***  que é quando a engine do JavaScript não reconhece o que foi atribuido.
Ainda ficou faltando falar como fazer conversão de String para Number e como podemos fazer um typecast para **Integer** ao invés de **float**.


That's all folḱs! 

