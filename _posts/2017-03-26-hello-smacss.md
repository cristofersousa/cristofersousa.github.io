---
layout: post
title: "Hello SMACSS!"
date: 2017-03-26 16:10:32 -0300
categories: css
---

![](https://i.ytimg.com/vi/6co781JgoqQ/maxresdefault.jpg)

Pensando em um cenário da qual o time não sabe como será o tamanho do projeto, é notório que alguns times começam a escrever CSS sem avaliar a longo prazo como isso poderá ficar, e acabando considerando ter que fazer uma nova re-escrita de CSS para conseguir facilitar o processo de manutenção de folhas de estilos.

Foi pensando nisso que [Jonathan Snook](https://twitter.com/snookca) criou o [SMACSS](https://smacss.com/) na qual ele visa que independente do tamanho do seu projeto o conceito do SMACSS pode ser adotado, basicamente seu conceito trata-se de separação de diretórios para organizar melhor o CSS de seu projeto, pensando nisso você ganha alguns pontos extras durante a vida do seu projeto como:

- Escalabilidade, 
- Manutenibilidade
- Modularidade 
- Otimização 
- Especificidade 

Quando escrevemos CSS é notório encontrar **!important** perdidos pelas folhas de estilo, pois você perdeu a regra de **especificidade** do elemento que estava tentando customizar, além disso precisa pensar em fazer com que sua folha de estilo ofereça **modularidade** para reaproveitar o estilo do seu componente em outras páginas (reaproveitamento), também é importante pensar em **manutenibilidade**, estou trabalhando com arquivo de 1500 linhas eu alterando essa classe será que ela estará repercurtindo por todo o projeto que a usa? E se foi criado o mesmo componente duas vezes, qual o nome da classe desse componente? E por último e não menos importante temos a **otimização**, se o seu CSS estiver orgarnizado para a engine dos browser será muito mais fácil fazer a leitura o que garante um "cross-browser" mais assertivo.

Entretanto o SMACSS não fornece um padrão de nomenclatura ele deixa que você escolha padrão deseja adotar se será uma metodologia ou algum padrão particular do próprio desenvolvedor.

Como estamos pensando em projetos de médio e grande porte, vamos considerar adotar uma metodologia que seja usual e qualquer pessoa do time que venha a escrever algo no CSS consiga ser o padrão, certo? Sendo assim, recomendo fortemente  que adote o padrão de nomenclatura [BEM](https://en.bem.info/methodology/quick-start/). 

Em outra oportunidade falarei sobre o BEM, outro ponto importante para que o SMACSS funcione
adequadamente e faça os **imports** dos diretórios do seu CSS é que adote um pré-processador como [http://sass-lang.com/](SASS) ou [Stylus](http://stylus-lang.com/) pois assim conseguirá fazer os imports de um diretório para outro, sem problemas. 

> Regra: SMACSS + BEM + STYLUS = 100% 

Voltando ao SMACSS, falamos que basicamente seu conceito é fazer separação de diretórios e quais são esses diretórios?

    - base  
    - layout
    - module
    - state
    - theme


**base** 
> Seria seus arquivos base da sua aplicação, o que é comum para todo o seu layout como Reset e Plugins

**layout **
> Seria a parte da estrutura do seu projeto, aqui entrará o CSSGrids, FlexBox e Position, a parte de header, footer, section. 

**module**
> Essa é a parte mais importante onde fica seus componentes como formulários, botões e etc.

**state**
> Aqui controlamos o estado do nosso componente e.g.


```

/* =======================
    States Rules
==========================*/

.is-visible {
    display: block
}

.is-hidden {
    display: none;
}

```

**theme**
> Aqui é onde você pode criar temas (pensando em claro ou escuro), não é obrigatório pela regra do SMACSS mas você acaba tendo essa opção.

E com isso concluímos o que precisamos saber sobre SMACSS! ;) 

That's all folks! 

