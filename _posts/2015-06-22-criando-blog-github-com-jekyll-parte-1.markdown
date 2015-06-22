---
layout: post
title:  "Criando um blog com o Github - Part 1"
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

## Renomeando o Repositório
Uma vez que fez um fork do repositório, você vai precisar ir nas configurações do seu novo repositório e o renomear para [username].github.io onde username você coloca o nome que desejar para o seu blog. O seu blog vai estar no endereço http://[username].github.io.
No entanto, antes de olharmos para o seu blog, vocÊ precisa de alguns minutos para configurar alguns items no arquivo de configuração _config.yml.



You'll find this post in your `_posts` directory - edit this post and re-build (or run with the `-w` switch) to see your changes!
To add new posts, simply add a file in the `_posts` directory that follows the convention: YYYY-MM-DD-name-of-post.ext.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
