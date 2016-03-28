---
layout: post
title:  "Exceções do this em Javascript"
date:   2016-03-14 10:15:00
categories: github javascript this exceçoes keyword
tags: github javascript this exceções keyword
published: true
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


## `this` Léxico

Funções normais continuam com as 4 regras que cobrimos no post anterior. Mas ES6 introduziu um tipo especial de função que não usa essas regras: `arrow-functions`.

`Arrow-functions` são sinalizadas não pelo palavra-chave `function`, mas por `=>`. No lugar de usar as quatros regras padrões, `arrow-functions` adotam a atribuição do `this` baseando-se no escopo delimitador(função ou global). Vamos ilustrar:

```js
function foo() {
    // retorna uma arrow function
    return (a) => {
        // `this` aqui é lexicamente adotado de `foo()`
        console.log( this.a );
    };
}

var obj1 = {
    a: 2
};

var obj2 = {
    a: 3
};

var bar = foo.call( obj1 );
bar.call( obj2 ); // 2, not 3!
```

A `arrow-function` criada em `foo()` lexicamente captura qualquer que seja o `this` de `foo()`. Desde que `foo()` teve o `this` como `obj1`, `bar` vai também ter o `this` como o `obj1`. O `binding` léxico da função arco não pode ser sobrescrito, mesmo com o `new`!.

O caso mais comum de uso será no uso de callbacks, tais como `event handlers` ou timers:

```js
function foo() {
    setTimeout(() => {
        // `this` aqui é lexicamente adotado de foo
        console.log( this.a );
    },100);
}

var obj = {
    a: 2
};

foo.call( obj ); // 2
```

Enquanto funções arco nos dão uma alternativa com relação à usar o `bind(..)` na função para garantir o valor do `this`, o que pode ser atraente, é importante notar que dessa forma estamos basicamente desabilitando o mecanismo do `this` em favor de um escopo léxico mais amplamente entendido. Antes do EcmaScript 6 nós tinhamos como fazer esse padrão, que é quase indistinguível do espírito das funções arco do Ecmascript 6: 

```js
function foo() {
    var self = this; // captura léxica do `this
    setTimeout( function(){
        console.log( self.a );
    }, 100 );
}

var obj = {
    a: 2
};

foo.call( obj ); // 2
```

Bom pessoal, acho que é isso. São muitos detalhes a aprender e espero que tenham gostado. Acredito que irei continuar escrevendo sobre javascript e nos vemos no próximo post. Abraço!
