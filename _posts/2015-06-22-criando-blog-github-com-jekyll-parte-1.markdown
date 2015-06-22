---
layout: post
title:  "Criando um blog com o Github e Jekyll - Part 1"
date:   2015-06-22 10:15:00
categories: github blog
---

Bem vindos a primeira lição de uma série sobre como criar um blog usando o github. O github tem uma ótima opção grátis para hospedar um blog e o melhor é que pode fazer isso em poucos minutos.Essa série vai cobrir tudo que precisa saber para hospedar, gerenciar e customizar o seu blog no Github.

## 1. Visão Geral

Github usa uma engine chamada Jekyll que transforma linguagem de marcação em páginas Html estáticas. A vantagem disso está na performance que é melhor desde que você está apenas servindo html e não tem de se preocupar com hospedagem ou banco de dados. 

A maneira mais fácil e rápida de começar com Jekyll é fazer um fork de um repositório Jekyll existente. Fork no git significa criar uma cópia do repositório para sua conta.

O repositório que iremos usar para dar o fork é o "Jekyll Now" que se encontra em https://github.com/barryclark/jekyll-now.
Um repositório baseado no Jekyll inclui muitas funcionalidades úteis para um blog tais como: Um tema bonito, marcador de código, botões para redes sociais, Api de comentário Disqus e Google analytics.

## 2. Fork do Repositório
Fazer um fork no Github é muito fácil. Vá até https://github.com/barryclark/jekyll-now e clique no botão de fork no github. Github vai criar uma cópia do repositório na sua conta. 

 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/fork_image.png); display:block;width:100px; height: 40px;">
</a>
</figure>

## 3. Renomeando o Repositório
Uma vez que fez um fork do repositório, você vai precisar ir nas configurações do seu novo repositório e o renomear para [username].github.io onde username você coloca o nome que desejar para o seu blog. O seu blog vai estar no endereço http://[username].github.io.

#### 3.1 Vá até settings
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/github_settings.png); background-size: 100%; display:block;width:100%; height: 350px;">
</a>
</figure>

#### 3.2 Mude o nome
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/github_rename_blog.png); background-size: 100%; display:block;width:100%; height: 165px;">
</a>
</figure>

No entanto, antes de olharmos para o seu blog, você precisa de alguns minutos para configurar alguns items no arquivo de configuração _config.yml.

## 4. Configurando o Repositório

 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/github_config.png); background-size: 100%; display:block;width:100%; height: 355px;">
</a>
</figure>

Tem algumas valores que você pode mudar:
<ul>
  <li>name - é o titulo do blog</li>
  <li>description - é a descrição do blog</li>
  <li>url - é a url do blog, que vai ser [username].github.io</li>
</ul>

Opcionalmente você pode configurar suas redes sociais que são mostradas na base do blog por preencher as contas na seção "footer-links" do arquivo _config.yml. Você pode editar o arquivo _config.yml diretamente no github. Uma vez feitas as alterações clique no botão verde para comitar.

## 5. Acessando o seu blog
Agora o seu blog está pronto. Abra o browser e navegue para http://[username].github.io, trocando [username] pelo username que escolheu anteriormente. 
 
## 6. Conclusão

Em poucos minutos nós criamos o seu blog e colocamos para rodar. No decorrer dos próximos posts, você aprenderá como gerenciar, criar novas páginas, customizar o tema, e customixar o domínio do seu blog. 

No próximo post iremos criar nossa primeira página. 
