---
layout: post
title:  "Curso de Git - Parte 2 - Instalando e configurando o Git"
date:   2015-06-28 10:15:00
categories: github blog git 
tags: github blog git
published: true
---

Olá pessoal, nesse post iremos começar a ver como usar o git para o versionamento de nosso código. Espero que gostem.

## Instalando e configurando o Git
O Git é um software assim como qualquer outro. Por isso é necessário que façamos a instalação do mesmo no nosso computador. Mostrarei agora como fazer isso para Windows, Mac e Linux.

#### Instalando no Linux
Para instalar o Git no Ubuntu ou outra distribuição Debian, execute o seguinte no terminal:
{% highlight ruby %}
sudo apt-get install git
{% endhighlight %}

no Fedora, execute o seguinte:
{% highlight ruby %}
sudo yum install git
{% endhighlight %}

Para as demais distribuições, veja o comando em: [http:// git-scm.com/download/linux](http:// git-scm.com/download/linux)

#### Instalando no Mac
Existem diversas maneiras de instalar o Git no Mac. A mais fácil é provavelmente instalar a ferramenta **Xcode Command Line Tools**. No Mavericks (10.9) ou acima dessa versão vocÊ pode simplesmente tentar rodar algum comando git via terminal. Caso não tenha instalado ele vai perguntar se deseja instalar.

Se preferia uam versão mais recente, você pode intalar via o binário. Um instalador Git para OSX é mantido e está disponível para download no site do Git, o link é [http://git-scm.com/download/mac](http://git-scm.com/download/mac)

Ou vocÊ pode baixar o instalador gráfico do Git para o Mac a partir do link: [https://code.google.com/p/git-osx-installer/downloads](https://code.google.com/p/git-osx-installer/downloads)

#### Instalando no Windows
Também existem diversas maneiras de instalar o Git no Windows. VocÊ pode ir no site [http://git-scm.com/download/win](http://git-scm.com/download/win) e o download vai começar automaticamente. 

Outra maneira fácil de ter o Git instalado é por instalar o Github para Windows. O instalador inclui uma versão de linha de comando do Git assim com interface gráfica. Você pode fazer o download no link [http://windows.github.com](http://windows.github.com)

## Configurando o Git
Agora que você tem o Git em seu sistema, você pode querer fazer algumas coisas para customizar seu ambiente Git. Você só precisa fazer uma vez; as configurações serão mantidas entre atualizações. Você também poderá alterá-las a qualquer momento executando os comandos novamente.

#### Identidade
A primeira coisa que você deve fazer quando instalar o Git é definir o seu nome de usuário e endereço de e-mail. Isso é importante porque todos os commits no Git utilizam essas informações, e está imutavelmente anexado nos commits que você realiza:

{% highlight ruby %}
$ git config --global user.name "Valter Junior"
$ git config --global user.email valter.junior@github.io
{% endhighlight %}

Relembrando, você só precisará fazer isso uma vez caso passe a opção --global, pois o Git sempre usará essa informação para qualquer coisa que você faça nesse sistema. Caso você queira sobrepor estas com um nome ou endereço de e-mail diferentes para projetos específicos, você pode executar o comando sem a opção --global quando estiver no próprio projeto.

#### Editor
Agora que sua identidade está configurada, você pode configurar o editor de texto padrão que será utilizado quando o Git precisar que você digite uma mensagem. Por padrão, Git usa o editor padrão do sistema, que é geralmente Vi ou Vim. Caso você queira utilizar um editor diferente, tal como o Emacs, você pode executar o seguinte:

{% highlight ruby %}
$ git config --global core.editor emacs
{% endhighlight %}

#### Verificando Suas Configurações
Caso você queira verificar suas configurações, você pode utilizar o comando git config --list para listar todas as configurações que o Git encontrar naquele momento:

{% highlight ruby %}
$ git config --list
user.name=Valter Junior
user.email=valter.junior@github.io
color.status=auto
color.branch=auto
color.interactive=auto
color.diff=auto
...
{% endhighlight %}

Bom galerinha, é isso por esse post. No próximo vamos começar a colocar a mão na massa! Até lá. ;)


