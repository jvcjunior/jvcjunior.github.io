---
layout: post
title:  "Criando um blog com o Github e Jekyll - Parte 2 - Criando seu primeiro Post"
date:   2015-06-22 13:15:00
categories: github blog jekyll
---

Bem vindos a segunda lição de uma série sobre como criar um blog usando o github. O github tem uma ótima opção grátis para hospedar um blog e o melhor é que pode fazer isso em poucos minutos.Essa série vai cobrir tudo que precisa saber para hospedar, gerenciar e customizar o seu blog no Github. Nesse post você irá criar o seu primeiro post.

## 1. Visão Geral
Nós vamos fazer todos os passos para criar um novo post, adicionar metada tais como titulo, categorias, tags, data e então colocar o post no ar. 

## 2. Criando o Arquivo
O primeiro passo é criar um arquivo para colocar o conteúdo do post do blog. No Jekyll todos os post são arquivos de marcação e estão armazenados no diretório _post. Quando comitamos nossos arquivos no Github, será compilado para um html estático.

O nome do arquivo está no formato ano-mes-dia-titulo-separado-por-tracos.md

{% highlight ruby %}
2015-06-22-meu-primeiro-post.md
{% endhighlight %}

Vamos criar nosso primeiro post.

1. Para criar o arquivo abra o browser e navegue para o seu repositório [username.github.io].
2. Vá até o diretório _post e clique no íconed + para adicionar um arquivo.
3. Nomeie o arquivo yyyy-mm-dd-meu-primeiro-post.md.
4. Preste atenção a proxima seção e preencha os metadados sobre o post(ie:titulo, data, categorias, etc)

## 3. Criando o metadata
Agora precisamos definir algumas informações sobre o nosso post. Todas as informações tais como título, categorias, data de publicação, etc são armazenadas no topo do arquivo e é chamado Front Matter.

Para definir a seção Front Matter você tem uma linha com 3 traços nela e o mesmo se repete no final da seção.
Abaixo estão metadados comuns que você deve preencher:

1. layout: é o nome do layout do diretório _layouts. Se seguiu a parte 1 e deu um clone no repositório jekyll-now, então o nome é post.
2. title: o título do post que será mostrado no blog. Tem de ser entre parênteses para evitar conflito com os parametros do front matter.
3. published: true or false. Determina se o post vai ser mostrado ou não.
4. date: data do post. Isto é opcional e se vocÊ não usar será usada a data que está no nome do arquivo.
5. categories: Lista de categorias delimitadas por virgulas. Colocar entre [] para multi categorias. É opcional mas recomendado.
6. tags: Lista de tags que serão usadas para construir a nuvem de tags.  É opcional mas recomendado.

#### Exemplo do Front Matter
{% highlight ruby %}
---
layout: post
title: Meu primeiro Post
published: false
date: 2015-02-01
categories: [blogging]
tags: [blogging]
---

Agora você pode criar o conteúdo do seu post
{% endhighlight %}

## 4. Criando  o conteúdo

## 5. Salvar como rascunho

## 5. Publicando o post

 ## 6. Conclusão


