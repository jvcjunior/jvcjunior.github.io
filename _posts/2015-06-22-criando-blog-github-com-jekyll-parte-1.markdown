---
layout: post
title:  "Criando um blog com o Github e Jekyll - Part 1"
date:   2015-06-22 10:15:00
categories: github blog
---

Bem vindos a primeira lição de uma sério sobre como criar um blog usando o github. O github tem uma ótima opção grátis para hospedar um blog e o melhor é que pode fazer isso em poucos minutos.Essa série vai cobrir tudo que precisa saber para hospedar, gerenciar e customizar o seu blog no Github.

## Visão Geral

Github usa uma engine chamada Jekyll que transforma linguagem de marcação em páginas Html estáticas. A vantagem disso está na performance que é melhor desde que você está apenas servindo html e não tem de se preocupar com hospedagem ou banco de dados. 

A maneira mais fácil e rápida de começar com Jekyll é fazer um fork de um repositório Jekyll existente. Fork no git significa criar uma cópia do repositório para sua conta.

O repositório que iremos usar para dar o fork é o "Jekyll Now" que se encontra em https://github.com/barryclark/jekyll-now.
Um repositório baseado no Jekyll inclui muitas funcionalidades úteis para um blog tais como: Um tema bonito, marcador de código, botões para redes sociais, Api de comentário Disqus e Google analytics.

## Fork do Repositório
Fazer um fork no Github é muito fácil. Vá até https://github.com/barryclark/jekyll-now e clique no botão de fork no github. Github vai criar uma cópia do repositório na sua conta. 

 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/fork_image.png)">
   <span class="hidden">{{site.author}}'s Picture</span></a>
</figure>

## Renomeando o Repositório
Uma vez que fez um fork do repositório, você vai precisar ir nas configurações do seu novo repositório e o renomear para [username].github.io onde username você coloca o nome que desejar para o seu blog. O seu blog vai estar no endereço http://[username].github.io.
No entanto, antes de olharmos para o seu blog, vocÊ precisa de alguns minutos para configurar alguns items no arquivo de configuração _config.yml.

## Configurando o Repositório

There is only 3 values that you are going to want to change:

name - this is the blog title
description - this is the tag line
url - this is the url of the blog, will be [username].github.io.
Optionally, you can also configure your social networks that show up in the footer of the site by filling in the various account names in the "footer-links" section of the _config.yml file.

You can edit the _config.yml directly in Github. Click on the file and then click the github edit file button icon. Once you have completed your edits, click the green commit button at the bottom of the screen.

## Acessando o seu blog
Agora o seu blog está pronto. Abra o browser e navegue para http://[username].github.io, trocando [username] pelo username que escolheu anteriormente. 
 
## Conclusão

EM poucos minutos nós criamos o seu blog e colocamos para rodar. No decorrer dos próximos posts, você aprenderá como gerenciar, criar novas páginas, customizar o tema, e customixar o domínio do seu blog. 

No próximo post iremos criar nossa primeira página. 
