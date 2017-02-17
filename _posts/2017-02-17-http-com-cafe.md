--- 
layout: post
title: "HTTP com Café" 
date: 2017-02-17 16:10:32 -0300 
categories: web, http, 
---

![](https://si.wsj.net/public/resources/images/OD-BI189_WINE_J_20151028164136.jpg)

Como assim em pleno 2017 alguém ainda quer falar sobre HTTP e seus protocolos?
O mundo falando sobre HTTP/2, RESTFull API e eu falando sobre HTTP, por que? 

Acho relevante falar sobre os "primórdios, pois acho que você deve se indagar o porque dessas novas tecnologias? Em qual momento o HTTP/1 deixou de ser interessante, sabendo isso, fica mais claro o que fazer daqui para frente com suas aplicações e como melhorar esse processo:

- Cliente-Servidor
- O que é HTTP
- Protocolo Get/POST
- Métodos

### Cliente-Servidor

Quando abrimos um navegador(browser) e inserimos na barra de endereço uma URL, inserimos tantas informções naquele curto espaço de tempo que toda a infra-estrutura senão estiver pronta para atender prontamente resulta em um 404 ou 500. 

No caso estamos falando de uma simples conexão Cliente-Servidor, onde Cliente é seu browser(Google Chrome, Mozilla Firefox ou o Microsoft Edge) e Servidor são ás aplicações funcionando com Java, PHP, .Net e entre outros.


### HTTP

HTTP ou Hypertext Transfer Procolo (Protocolo de Transferência de Hipertexto), nada mais é que um ***protocolo**  que define as *** regras de comunicação ** entre ***cliente-servidor** na web e esse protocolo é o mais importante na internet por conta disso.

O papel do HTTP é consolidar a comunicaço entre o cliente-servidor, existem outros inúmeros protocolos para outros fins, mas o mais importante para nós é entendermos o que rola com o HTTP. Além dessa "padronização de comunicação" ele é responsável por enviar(get/post) e receber dados a partir dessa conexão. 

Ok, aí você vai perguntar mais e o ***HTTPs ** ?
Ele não se trata de outro procoloco ele continua sendo o HTTP porém com uma camada de segurança, quando enviamos informações para o servidor da qual não possui https,estamos enviando texto puro é aí que fica o risco, qualquer pessoa, pode pegar o que você está enviando para esse site e manipular as informações da forma que achar conveniente. Uhn, quer saber mais sobre isso dê uma lida depois sobre Criptografia e Segurança (chave pública e chave privada0. ;) 


Voltando ao protocolo HTTP, temos a URL http://www.opensanca.com.br:80/jobs

Essa url tem um endereço fisico (IP) + DNS + porta + recurso

***Dominio:** É o nome do site na Web. Ele facilita a navegação do usuário que não precisa lembrar o IP de cada site
***DNS:** Tem como função realizar a tradução do nome de um domínio para o endereço de IP correspondente. O protocolo que serve para transferir arquivos é o FTP (File Transfer Protocol)
***Porta:** A porta reservada para o protocolo HTTP é o 80. Novamente um número, e como o navegador já sabe essa porta padrão podemos omiti-la, mas nada nos impede adicioná-la no endereço.
***Recurso:** Um recurso é algo concreto na aplicação que queremos acessar






