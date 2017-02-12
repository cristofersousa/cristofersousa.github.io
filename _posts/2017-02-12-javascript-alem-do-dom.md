--- 
layout: post title: "JavaScript além do DOM." 
date: 2017-02-12 18:15:32 -0300 
categories: javascript 
---

# JavaScript - Fundamentos de Orientação a Objetos

Pense em uma biblioteca, agora imagine cada livro da biblioteca, para que eu possa ter uma biblioteca é necessário que exista livros e desses livros, autores e uma editora, isso é o "básico" que toda biblioteca deve ter para que ela seja denominada de biblioteca.

Agora e se quisermos transformar isso para o cenário da computação. Cada livro se trata de um objeto, essa abstração faz com que seja possivel que possamos adotar padrões que são caracteristicas do mundo real, assim como seu objeto e suas funções.

###  Os 04 principais conceitos de Orientação a Objetos:

 - Abstração
 - Herança
 - Polimorfismo
 - Encapsulamento


#### Abstração

Abstração é o processo de você conseguir abstrair uma estrutura que contenha as condições necessárias daquele objeto do mundo real, para o contexto da programação.

> Ex: Biblioteca é constituida por livros.

#### Herança

Se pensar no cenário do mundo real, você está herdando alguma coisa de alguém certo?
Na programação o cenário é o mesmo, podemos assumir que um objeto é elemento Pai e que os elementos filhos herdam comportamentos e métodos do pai.

> Ex: Autores possuem uma herança de livros, isto é posso saber de um determinado autor quais livros foram escrito por ele.


#### Polimorfismo

É a caracterisitca (comportamento) da qual seres podem assumir mais de uma forma, de modo geral obejtos que contém níveis mais altos de abstração e instanciam níveis mais baixos de abstração.

> Ex: Editora pode ter livros somente de informática, como depois pode ter livros ligado a gastronomia.

### Encapsulamento

Pense, todo livro possui sua estória e seu contexto, mas necessariamente você não precisa ler o livro todo para saber do que se trata, a contra-capa fornece essa informação, e como seria isso para a computação? Esse é o conceito de encapsulamento, o objeto deve expor somente o necessário, sem a necessidade de contar como algo foi realizado, você apenas o consome. ;)


#### Tipos Primitivos em JavaScript

Bom o JavaScript é Orientado á objetos, existem 05 tipos:  `strings, number, boolean, null e undefined`, os 3 primeiros informados conseguem ser representados como objetos, seja por criação ou transformação, que ocorrem durante o interpretador do JavaScript para que possamos ter acesso a determinados métodos da linguagem.

 A beleza do JavaScript está que tudo são objetos, são apenas associações de chave:valor, semelhante a Arrays associativos. O valor pode assumir desde estruturas simples como strings e números até estruturas complexas, como objetos ou até mesmo funções.


Por que JavaScript é considerada uma linguagem rápida? O fato dela ser rápida é pelo motivo dela ser interpretada e não compilada como a maioria.  

JavaScript possui dois tipos de objetos `Nativo` ( definido pelo ES ou criado pelo programador) e `Hospedeiro` (definidos pelo ambiente, browser insere seus objetos como windows e todos os objetos DOM)
