---
layout: post
title:  "Mapeamento GORM para herança - Herança ou Composição no Grails"
date:   2015-06-23 10:15:00
categories: grails gorm heranca
---

Fala pessoal, hoje me deparei com um problema ao usar GORM(Grails Object Relation Mapping) para mapear uma herança e gostaria de compartilhar o que aprendi.

## 1. Problema
Eu tenho de adicionar no sistema duas tabelas que compartilham cerca de 6 atributos. 

{% highlight ruby %}
class classe1{
     attr1,attr2,attr3,attr4,attr5,attr6,
     attr7
}

class classe2{
     attr1,attr2,attr3,attr4,attr5,attr6,
     attr8
}
{% endhighlight %}

Para evitar a duplicação de código resolvi tentar criar uma modelagem de modo que eu não precisasse replicar os atributos nas duas classes que criei. 

## 2. Primeira Tentativa : Herança
Pensei logo em fazer uma classe intermediária com os atributos compartilhados e fazer outras classes que tem esses atributos herdarem da mesma. 

{% highlight ruby %}
class classe_base{
    attr1,attr2,attr3,attr4,attr5,attr6
}

class classe1 extends classe_base{
    attr7
}

class classe2 extends classe_base{
    attr8
}
{% endhighlight %}

## 3. Criando o metadata

#### 3.1 Vá até settings

## 4. Criando  o conteúdo

## 5. Salvar como rascunho

## 5. Publicando o post

 ## 6. Conclusão


