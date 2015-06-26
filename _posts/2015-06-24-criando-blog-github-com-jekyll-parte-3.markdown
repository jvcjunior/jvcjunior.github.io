---
layout: post
title:  "Criando um blog com o Github e Jekyll - Parte 3 - Adicionando comentários ao Post"
date:   2015-06-24 10:15:00
categories: github blog jekyll disqus
tags: github blog jekyll disqus
published: true
---

Bem vindos a terceira lição de uma série sobre como criar um blog usando o github. O github tem uma ótima opção grátis para hospedar um blog e o melhor é que pode fazer isso em poucos minutos. Essa série vai cobrir tudo que precisa saber para hospedar, gerenciar e customizar o seu blog no Github. Nesse post você irá aprender a adicionar no seu blog a possibilidade de usuários comentarem. 

## 1. Visão Geral
Você talvez ache que comentários não são muito importantes mas pode ter certeza que são a chave para que você tenha a capacidade de interagir com seus leitores. Usuários querem ter conversas com você sobre aquilo que escreveu. Vai ser bom para você também para que possa aprender com eles também.

Infelizmente o Jekyll por si só não fornece essa funcionalidade. Porém, é relativamente fácil adicionar essa habilidade, graças a uma ferramente chamada Disqus.  

Nós iremos passar pelo processo de criar uma conta Disqus, configurar a conta, configurar seu blog e testar tudo. 

## 2. Configurando Disqus
1. Abra o browser e navegue para [https://disqus.com/admin/signup/?utm_source=New-Site](https://disqus.com/admin/signup/?utm_source=New-Site)
2. Crie sua conta.
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/sign-up-disqus.png); background-size: 100%; display:block;width:100%; height: 350px;">
</a>
</figure>

3. Preencha as informações conforme mostra na imagem abaixo e clique em finalizar. Obs: Você não conseguirá mudar a disqus url. Esse valor será único para todos os seus sites. Você pode ter multiplos sites usando uma mesma conta. 
 <figure>
   <a class="img" href="{{ site.baseurl }}" style="background-image: url(/assets/images/create-site-account-disqus.png); background-size: 100%; display:block;width:100%; height: 350px;">
</a>
</figure>

4. Você irá se deparar com a tela "Escolha sua plataforma". Não se preocupe com nenhuma dessas opções porque não iremos usá-las. 

5. Clique na aba "General" no lado esquedo do título "Escolha sua plataforma".

6. Dê um scroll no site até achar a seção "Site Identity" e preencha os dados corretamente. O nome do site será o nome que aparecerá no seu blog quando os comentários aparecerem. Preste atenção ao seu "shortname" porque ele será usado mais adiante quando formos configurar o blog para mostrar os comentários.

7. Dê um scroll novamente no site até achar a seção "Community Rules"e marque o seguinte:
 - pre-moderation: all
 - Links in comments: yes
 - guest commenting: false

Para evitar comentários com spams é melhor ter de aprovar os comentários antes de mostrar no blog. 

8. Dê um scroll novamente no site até achar a seção "Social Platform Intergration" e adicione sua conta do twitter se você tiver uma. 

9. Clique no botão de salvar.


## 3. Configurando seu blog
1. Abra o browser e navegue para seu repositorio [username].github.io.
2. Clique no arquivo _config.yml para abri-lo
3. Clique no botão de edição
4. Procure pela palavra disqus. Depois coloque nesse parametro o seu disqus shortname. Por exemplo:
 {% highlight ruby %}
disqus: jvcjunior
{% endhighlight %}

5.
6.
7.
8.

## 4. Testando
