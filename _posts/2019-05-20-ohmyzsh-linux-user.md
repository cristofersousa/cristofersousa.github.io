--- 
layout: post
title: "Terminal com Oh My ZSH para Linux" 
date: 2019-05-20 11:04:32 -0300 
categories: linux, terminal, bash,
---


## Instalando o zsh no Linux
Alguns distros Linux já possuem o zsh pré-instalado. Você pode verificar se existe, assim como sua versão, escrevendo zsh --version em uma janela de terminal . Caso esta versão do zsh esteja ok para você, já está tudo pronto! Caso contrário vamos instalar.

Mas antes veja qual distribuição Linux você está usando. Veja Lista de distribuições Linux - Wikipedia para uma lista. A maioria dos sistemas Linux - incluindo o Ubuntu e Mint - são baseados no Debian .

## Sistemas Linux baseados em Debian
Ubuntu, Linux Mint, ElementaryOS e muitos outros

Abra uma janela de terminal . Copie e cole o seguinte código na janela do terminal e tecle emENTER . 

Com o comando SUDO pode ser solicitado a senha do Administrador
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install zsh
sudo apt-get install git
Sistemas Linux baseados em Red Hat
Fedora e CentOS são os mais famosos
```

Abra uma janela de terminal . Copie e cole o seguinte código na janela do terminal e tecle emENTER .
```
sudo yum upgrade
sudo yum install zsh
sudo yum install git
Sistemas linux baseados em Suse
``` 
Abra uma janela de terminal . Copie e cole o seguinte código na janela do terminal e tecle emENTER .
```
sudo zypper upgrade
sudo zypper install zsh
sudo zypper install git
Instalando OH MY ZSH
```
Abra uma janela de terminal . Copie e cole o seguinte código na janela do terminal e tecle emENTER .

> sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
