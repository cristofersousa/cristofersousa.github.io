---
layout: post
title: "Hello SMACSS!"
date: 2017-03-26 16:10:32 -0300
categories: css
---

![](https://i.ytimg.com/vi/6co781JgoqQ/maxresdefault.jpg)

Pensando em um cenário da qual o time não sabe como será o tamanho do projeto é notório que alguns dev's comecem a escrever CSS sem avaliar a longo prazo como isso poderá ficar e com terão que fazer uma nova re-escrita de CSS para conseguir facilitar o processo de manutenção das folhas de estilos do projeto.

Foi pensando nisso que [Jonathan Snook](https://twitter.com/snookca) criou o [SMACSS](https://smacss.com/) da qual ele visa que você pode adota-lo independente do tamanho do seu projeto. Basicamente seu conceito  é exclusivamente tratar da separação de diretórios para organizar melhor o CSS, a partir disso você ganha alguns pontos extras na vida do projeto como:

- Escalabilidade, 
- Manutenibilidade
- Modularidade 
- Otimização 
- Especificidade 

Sobre **escalabilidade**, seu projeto pode crescer de tamanho a qualquer momento que você conseguirá escalar ele sem problemas pois ele foi pensado para isso, desde o seu inicio, lembre-se dessa frase do Jonhn Resig - Write less, do more!.

Sobre **especificidade**, quando varremos alguns projetos de CSS por aí é notório encontrar **!important** perdidos pelas folhas de estilo, pois provavelmente você perdeu a regra de especificidade do elemento que estava tentando customizar.

Sobre **modularidade**, precisa ficar claro para o time que sua folha de estilo ofereça isso, pois assim pode reaproveitar o estilo do seu componente em outras páginas (reaproveitamento).

Sobre **manutenibilidade**, cogite que você esteja trabalhando com um único arquivo de 1500 linhas e a cada alteração essa classe deveria repercurtir por todo o projeto e aí você descobre que não ocorre! Aí, surge a sua pergunta, quais são as classes que manipula esse elemento que é idêntico a este que estou alterando? 

Sobre **otimização**, se o seu CSS estiver organizado, possivelmente o render do browser será muito mais fácil, pois irá fazer a leitura adequadamente e garantindo assim um "cross-browser" mais assertivo, lembre-se **Normalize & RESET**, é apenas o primeiro passo para garantir cross-browser, os outros 99% do projeto está na sua forma de escrever o CSS.

Sobre tudo, o SMACSS não fornece um padrão de nomenclatura, o foco dele é **dividir para conquistar** e com isso ele deixa livre á sua escolha qual será a forma de escrita de seu CSS. Como estamos pensando em projetos de médio e grande porte vamos considerar adotar uma metodologia que seja usual e que qualquer pessoa do time que venha a escrever algo no CSS consiga perpetuar este padrão, certo? 

Sendo assim, recomendo fortemente que adote o padrão de nomenclatura [BEM](https://en.bem.info/methodology/quick-start/), em outra oportunidade falarei como ele funciona, outro ponto importante para que o SMACSS funcione adequadamente e faça os **imports** dos diretórios do seu CSS é que adote um pré-processador como [Sass](http://sass-lang.com/) ou [Stylus](http://stylus-lang.com/) pois assim conseguirá fazer os importação do arquivos sem problema. 


> Regra geral para SMACSS: BEM + STYLUS = 100% 

Voltando ao SMACSS, falamos que basicamente seu conceito é fazer separação de diretórios e quais são esses diretórios?

    - base  
    - layout
    - module
    - state
    - theme


**base** 
> Seria seus arquivos base da sua aplicação, o que é comum para todo o seu layout como Reset e Plugins.

**layout**
> Seria a parte da estrutura do seu projeto, aqui entrará o CSSGrids, FlexBox, Position, Header, Footer e Section. 

**module**
> Essa é a parte mais importante onde fica seus componentes como formulários, botões, tipografia, cores e etc.

**state**
> Aqui controlamos o estado do nosso componente, pense no hover, active, disabled, é a parte do comportamento do componente sobre a aço do usuário por exemplo:
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
> Aqui é onde você pode criar temas pensando em theme-claro (pessoas que **preferem** layout mais claro/clean)  ou theme-escuro (pessoas que **preferem** layout mais escuros), é válido avaliar que durante todo o seu projeto deve ser considerado acessibilidade e essa parte do theme é bastante importante. Aqui você altera as cores prevendo como deveria se comportar o layout para pessoas com deficiência visual ou luminosidade do ambiente. Por default essa regra não é obrigatória para usar o SMACSS mas ele já prevê isso para você caso seja necessário! ;)

E com isso concluímos o que precisamos saber sobre SMACSS! 

That's all folks! 

