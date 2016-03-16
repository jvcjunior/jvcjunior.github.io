---
layout: post
title:  "Exceções do this em Javascript"
date:   2016-03-14 10:15:00
categories: github javascript this exceçoes keyword
tags: github javascript this exceções keyword
published: false
---

Fala galera, beleza? Visto que o no último post falei que o `this` em javascript tem algumas exceções, vou falar sobre elas hoje.

## Exceções relacionadas com o `this`
Como costume, toda regra tem exceções. E não é diferente para as regras que vimos no post anterior. Alguns cenários o comportamento do `this` pode te deixar surpreso, onde você acredita que está sendo atribuido de uma forma mas acaba que a atribuição do `this` sai um pouco diferente do planejado. Vamos analisar esses casos. 

## `this` ignorado

Se passarmos `null` ou `undefined` como parâmetro do call, apply ou o bind, esses valores serão ignorados e o `binding` default vai ser aplicado. Vamos ver um exemplo:

```js
function teste() {
    console.log( this.a );
}

var a = 2;

teste.call( null ); // 2
```
