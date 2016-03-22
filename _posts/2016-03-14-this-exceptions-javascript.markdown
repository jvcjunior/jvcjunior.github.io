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

## `this` seguro

Talvez uma prática "segura" seja passar especificamente um objeto para inicialização para o `this` que seja garantido não ser um objeto que crie efeitos colaterais no nosso programa. Nada mais especial do que um objeto completamente vazio

Onde quer que seja a chamada, a maneira mais fácil de criar um objeto totalmente vazio é `Object.create(null)`. `Object.create(null)` é similar ao `{ }`, mas sem o `delegation` para `Object.prototype`, logo é um vazio "mais vazio" que somente o `{ }`. Vamos ver um exemplo: 

```js
function foo(a,b) {
    console.log( "a:" + a + ", b:" + b );
}

var vazio = Object.create( null );

foo.apply( ø, [2, 3] ); // a:2, b:3

var bar = foo.bind( vazio, 2 );
bar( 3 ); // a:2, b:3
```

## Referências indiretas

Outra coisa que precisamos estar cientes é que você pode( intencionalmente ou não) criar referências indiretas a funções, e nesses casos, quando a referência é invocada, o `default binding` também é aplicado. 

Uma das maneiras mais comuns de referências indiretas ocorre da seguinte forma: 

```js
function teste() {
    console.log( this.a );
}

var a = 2;
var o = { a: 3, teste: teste };
var p = { a: 4 };

o.teste(); // 3
(p.teste = o.teste)(); // 2
```

O resultado dessa expressão `p.foo = o.foo` é uma referência para o objeto da função subjacente. Dessa maneira, o `call-site`, ou seja, o ponto de chamada é apenas `foo()`, e não `p.foo()` ou `o.foo()` como você pode esperar. Pelas regras acima,  o `default binding` é aplicado. 
