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
O conteúdo do post será escrito com marcação e ficará logo abaixo da seção front matter. Abaixo estão tags de marcações comuns que você usará. Cabeçalhos, listas, negrito, pontos, links e destaque de código.

#### Cabeçalhos
O símbolo # no ínicio da linha indica a criação de um cabeçalho e o número de # indica o tamanho da tag de cabeçalho.
{% highlight ruby %}
#  = h1
## = h2
e assim vai até h6
{% endhighlight %}

#### Listas ordenadas ou com pontos

Para pontos comece a linha com * ou -
{% highlight ruby %}
* item 1
* item 2
{% endhighlight %}

Fica dessa forma: 

* item 1
* item 2

Para lista ordenada começa com o número desejado
{% highlight ruby %}
1. item 1
2. item 2
{% endhighlight %}

Fica dessa forma: 

1. item 1
2. item 2

#### Negrito
Coloque 2 ** no ínicio e no fim do texto que deseja colocar negrito.
{% highlight ruby %}
**item**
{% endhighlight %}

Fica dessa forma:

**item**

#### Links
Links para outras páginas

{% highlight ruby %}
[nome do link a ser mostrado](http://url.com)
{% endhighlight %}

[nome do link a ser mostrado](http://url.com)

#### Code Highlighting
Use a marcação highlighter

## 5. Salvar como rascunho
Muitas vezes não iremos escrever e publicar um post de uma vez só. Pra isso é necessário você ter a capacidade de salvar um rascunho para ser publicado mais adiante. Para fazer isso basta você mudar o parametro published para false na seção front matter. Isso irá dizer para o Jekyll não publicar o seu post.

## 5. Publicando o post
Publicar o post é muito fácil. Basta você mudar o parametro published para true ou false na seção front matter. Depois faça um commit para que a mudança reflita em seu repositório. 

## 6. Conclusão
Esse post é uma lição chave para que aprenda a criar um novo post. Criar um novo post com o Jekyll é muito fácil e com um pouco de marcação fica mole. Uma vez que aprende as diferentes tags de marcação você escreverá o seu post em muito pouco tempo. 
A gente se fala no próximo post, onde iremos discutir sobre como adicionar comentários no seu post. Abraço!

