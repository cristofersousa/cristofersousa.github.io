--- 
layout: post
title: "CSS para Layout" 
date: 2017-02-14 16:10:32 -0300 
categories: css 
---
![](http://www.pngpix.com/wp-content/uploads/2016/07/PNGPIX-COM-Paper-Boat-PNG-Transparent-Image.png)

Quero falar sobre criação de layout com CSS como organizar os objetos no browser de forma correta e eficaz.
Levando em consideração medidas relativas _%, vh, vw, vmin e vmax_, irei fazer uma série de 03 posts abordando como compor sua interface, usando propriedades que a W3C possui:

  - [Position](https://www.w3.org/TR/css-position-3/)
  - [FlexBox](https://www.w3.org/TR/css-flexbox-1/)
  - [GridCSS](https://www.w3.org/TR/css-grid-1/)


Hoje, falaremos sobre a propriedade `position`. Para quem viveu apenas a era Flex-box ou para quem sempre teve dúvidas sobre como
funciona essa propriedade.

Basicamente essa propriedade serve para empilhar componentes e caixas "flutuantes" sobre a tela, isto é, ela fornece condições para 
que o desenvolvedor tenha plena condição de fazer uma espécie de lego no browser.

Essa propriedade pode assumir 04 valores possivéis: _Static, Relative, Fixed e Absolute_.

`Static:`
  o valor static é o valor padrão de todos os elementos HTML. Um elemento com position: static; não se posiciona de maneira especial, seria o mesmo que dizer que o elemento não tem posição definida ou então que um elemento com o atributo position definido seria posicionado.

`Relative:` 
  O valor relative se comporta igualmente ao static, a menos que se adicione propriedades extras no estilo do elemento.

`Fixed:`
  O valor fixed - é posicionado relativamente ao "viewport", isso significa que ele sempre ficará no mesmo lugar mesmo que haja rolagem na página. Assim como o relative, as propriedades top, right, bottom e left também são utilizadas.

`Absolute:`
  O valor absolute é o mais complicado. Este valor se comporta como o fixed, porém tendo como referência a posição do elemento relativo mais próximo de onde está contido, ao invés do viewport. Se um elemento position:absolute não possuir elementos ancestrais posicionados relativamente, ele utilizará o body como referência.

```
Ex: Absolute 

.relative {
  position: relative;
  width: 600px;
  height: 400px;
}

.absolute {
  position: absolute;
  top: 120px;
  right: 0;
  width: 300px;
  height: 200px;
}
``` 

Da parte de position é apenas isso? Parece que sim! ;) 
Até a próxima! 
