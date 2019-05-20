--- 
layout: post
title: "Terminal com Oh My ZSH para Mac" 
date: 2019-05-20 11:00:32 -0300 
categories: macosx, terminal, bash,
---


## Instalando Oh My ZHS no macOS


> Vamos instalar a versão mais recente através do Homebrew :

Passo 1 - Instale o Homebrew
Abra uma janela de terminal .

O Homebrew [...] simplifica a instalação de software no sistema operacional Mac OS X.

[- Homebrew - Wikipedia](http://en.wikipedia.org/wiki/Homebrew_%28package_management_software%29)

Copie e cole o seguinte código na janela do terminal e tecle enter.

> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Será solicitado instalação do Command Line Developer Tools da Apple. Confirme clicando em Instalar . Após o termino da instalação, continue a instalação Homebrew.

## Etapa 2 - Instale o zsh
*OS X vem pré-carregado com zsh.*
Você pode verificar sua versão escrevendo `zsh --version` em uma janela de terminal . 
Caso esta versão do zsh esteja ok para você, já está pronto! 
Caso contrário, copie e cole o seguinte código na janela do terminal e tecle enter.

> brew install zsh
Você pode usar o zsh agora.

## Etapa 3 - Instale o CURL
Copie e cole o seguinte código na janela do terminal e tecle enter.

> brew install curl

## Etapa 4 - Instale o OH MY ZSH
Copie e cole o seguinte código na janela do terminal e tecle enter.

> sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

Pronto agora o seu terminal do Mac ficou bem legal :)
