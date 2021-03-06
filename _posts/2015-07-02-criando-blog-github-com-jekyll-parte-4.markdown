---
layout: post
title:  "Criando um blog com o Github e Jekyll - Parte 4 - Adicionando outras páginas"
date:   2015-06-28 10:15:00
categories: github blog  
tags: github blog jekyll 
published: true
---

Bem vindos a quarta lição de uma série sobre como criar um blog usando o github. O github tem uma ótima opção grátis para hospedar um blog e o melhor é que pode fazer isso em poucos minutos. Essa série vai cobrir tudo que precisa saber para hospedar, gerenciar e customizar o seu blog no Github. Nesse post você irá criar novas páginas como a [Sobre](http://jvcjunior.github.io/about.html) que tem no meu blog.

## 1. Visão Geral
A medida que o seu blog cresce você vai querer adicionar informação além de somente posts. Se você começa a fazer palestras em eventos ou quer mostrar seu portfólio ou criar categorias para seus posts, você vai querer essas páginas separadas. 

## 2. Criando um arquivo por página
Se você tem lido os posts anteriores os passos serão familiares para você:

1. Abra o browser e navegue até o seu repositório [username].github.io.
2. Clique no botão + para adicionar um novo arquivo
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/new_page_button.png); background-size: 100%; display:block;width:100%; height: 90px;">
</a>
</figure>

3. Coloque que o nome: portfolio.md
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/new_page_name.png); background-size: 100%; display:block;width:100%; height: 90px;">
</a>
</figure>

## 3. Escolhendo o layout
Para dizer para a engine do jekyll qual vai ser o layout da página você precisa adicionar uma tag na seção front matter, como fizemos antes algumas vezes.

Da [Parte 2 - Criando seu primeiro Post](http://jvcjunior.github.io/github/blog/jekyll/2015/06/22/criando-blog-github-com-jekyll-parte-2.html) você vai lembrar que a seção front matter são os metadados relacionados com o post mas é usado pelo jekyll para qualquer página. Todas as tags da seção front matter são as mesmas para página assim como para posts.

Para mudar o layout da página vocÊ precisa mudar a tag layout da seção front matter para página ao invés de post.

Para que a página se torne disponível em [username].github.io/portfolio, você precisa colocar a tag **permalink** para /portfolio

## 4. Adicionando conteúdo
O conteúdo é escrito em linguagem de marcação assim como os posts. Na  [Parte 2 - Criando seu primeiro Post](http://jvcjunior.github.io/github/blog/jekyll/2015/06/22/criando-blog-github-com-jekyll-parte-2.html) nós estudamos sobre as marcações comuns.

Por enquanto adicione marcações simples como abaixo: 
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/portfolio_first_content.png); background-size: 100%; display:block;width:100%; height: 350px;">
</a>
</figure>

## 5. Preview da página
Para ver sua página navegue para http://[username].github.io/portfolio

## 6. Adicionando a página ao menu
Uma vez que você está pronto para compartilhar sua página com os leitores, você vai querer adicionar sua página ao seu menu e a ter indexada a engines de busca.

Para dizer para engines de busca para indexar a sua página, precisamos remover a tag sitemap:false

Para adicionar ao menu:

1. Navegue no repositório para o diretório _layout que está na página inicial de seu repositório
2. Clique na página default.html.
3. Clique no ícone para editar o arquivo
4. Encontre o menu principal. Você pode procurar pela seção home ou about
5. Adicione uma linha no menu na posição que desejar
6. Comite sua alteração
7. Agora navegue para o seu blog e veja se apareceu um item de menu com o nome que colocou

## 7. Conclusão
Em alguns passos fomos capazes de adicionar uma nova página ao blog. Você pode continuar a costruir seu portfólio com a marcação necessária para mostrar o seu portfolio ou você pode remover do menu até estar pronto para mostrar.

Na próxima seção iremos nos basear nessa lição para adicionar uma página de posts por categoria. Até mais!
