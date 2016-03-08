---
layout: post
title:  "Hoisting - Javascript"
date:   2016-02-02 10:15:00
categories: github javascript hoisting 
tags: github javascript hoisting
published: true
---

Fala galera, beleza? Fazia tempo que não escrevia nada e nesse tempo tenho me interessado bastante por Javascript. Tenho procurado aprender a fundo essa tecnologia e é por isso que hoje vou escrever algo sobre. Irei falar sobre uma caracteristica do Javascript que poucos conhecem e que pode evitar muitos problemas quando entendida. É fácil e basta um pouco de anteção. Vamos lá.

## Javascript Hoisting (Içamento, Levantamento)

Existe uma tentação de pensar que todo o código que você vê em um programa Javascript é interpretado linha a linha, de cima a baixo, a medida que o programa executa. Talvez esse pensamento tenha mais lógica, ou talvez por uma prévia experiência em linguagens as quais esse comportamento ocorre, como o C. 
Enquanto esse pensamento é parcialmente correto, há uma parte do que foi pressuposto que pode nos levar a um pensamento errado sobre o nosso programa; 
Considere por exemplo o código abaixo:
{% highlight ruby %}
a = 2;
var a;
console.log( a );
{% endhighlight %}

O que espera que será impresso no comando console.log(..) ?
Muitos desenvolvedores talvez esperassem: `undefined`, desde que `var a` vem depois de `a = 2`, e seria natural assumir que a variável é redefinida e por isso setada para `undefined`. No entanto a saída será `2`.
Considere esse outro pedaço de código:

{% highlight ruby %}
console.log( a );
var a = 2;
{% endhighlight %}

Você talvez fique tentado a assumir que, desde que o código anterior mostrou algo diferente do que o comportamento top-down, talvez nesse código, `2` também seja impresso. Outros talvez achem que a variável a é usada antes da declaração, logo deve resultar na exceção ReferenceError.
Infelizmente, ambos os ‘chutes’ estão incorretos. A saída seria undefined.
Então, o que está acontecendo aqui? O que vem primeiro, a declaração ou a atribuição? 
Bom, no Javascript todas as declarações, tanto de variáveis como de funções, são processadas primeiro, antes de qualquer parte do código ser executado. 
Quando você vê `var a = 2;`, provavelmente pensa nisso como uma expressão. Mas o Javascript pensa nessa expressão como se fossem duas expressões: `var a; e a = 2;`. A primeira expressão, a declaração, é processada durante a fase de compilação. A segunda expressão, a atribuição, é deixada no lugar para a fase de execução. 


Então naquele nosso primeiro exemplo de código, o Javascript que é visualizado dessa forma: 

{% highlight ruby %}
a = 2;
var a;
console.log( a );
{% endhighlight %}

na realidade faz isso:
{% highlight ruby %}
var a;
a = 2;
console.log( a );
{% endhighlight %}

onde a primeira parte é a compilação e a segunda parte a execução. Similarmente, nosso segundo exemplo:
{% highlight ruby %}
console.log( a );
var a = 2;
{% endhighlight %}

na realidade faria isso:
{% highlight ruby %}
var a;
console.log( a );
a = 2;
{% endhighlight %}

Então, uma maneira de pensar, meio que metaforicamente, sobre esse processo, é que a declaração de variáveis e funções se “movem” de onde aparecem no fluxo do código para o topo do código. Por isso o nome é “Hoisting”, o que significa Içar, Levantar.
Em outras palavras, a declaração vem antes da atribuição. 
Observação: Somente as declarações por si só são ‘içadas, levantadas’, enquanto qualquer atribuição ou outra lógica executável é deixada no lugar. Se o Içamento fosse reorganizar a execução lógica de nosso código, poderia causar alguns estragos. 

##Declaração de funções x Expressões de função

Pense no exemplo abaixo:
{% highlight ruby %}
teste();
function teste() {
    console.log( a ); // undefined
    var a = 2;
}
{% endhighlight %}

A declaração da função `teste` é ‘içada’, de tal maneira que a chamada pra teste na primeira linha possa ser executada. 
É importante notar que o ‘içamento’ é por escopo. Nossos exemplos anteriores foram simplificados duma maneira que só usamos o escopo global. A função `teste(..)` que estamos analisando agora expõe que var a é ‘içada’ para o topo de `teste(..)` (não, obviamente, para o topo do programa).O Javascript interpreta o código de teste da seguinte maneira: 
{% highlight ruby %}
function teste() {
    var a;
    console.log( a ); // undefined
    a = 2;
}
teste();
{% endhighlight %}

Declarações de funções são ‘içadas’ conforme vimos. Mas expressões de função não são.
{% highlight ruby %}
teste(); // not ReferenceError, but TypeError!
var teste= function bar() {
    // ...
};
{% endhighlight %}

O identificador da variável `teste` é ‘içado’ e setado ao escopo global do programa, então `teste()` não gera um  ReferenceError. Mas `teste` não tem valor ainda (como teria se fosse uma declaração de função ao invés de uma expressão). Então, `teste()` está invocando o valor `undefined` o que resulta em `TypeError`.
Também vamos lembrar que mesmo sendo uma expressão de função com nome, o identificador do nome não está disponível no escopo:

{% highlight ruby %}
teste(); // TypeError
bar(); // ReferenceError
var teste = function bar() {    // ...
};
{% endhighlight %}

O código abaixo mostra como o código acima é interpretado(com o içamento):

{% highlight ruby %}
var teste;

teste(); // TypeError
bar(); // ReferenceError

teste = function() {
    var bar = ...self...
    // ...
}
{% endhighlight %}

Um último detalhe. Vimos que tanto declarações de funções como de variáveis são ‘içadas’. Mas um detalhe sútil é que funções são ‘içadas’ primeiro, então depois são as variáveis. 
Conclusão
Bom pessoal, podemos perceber que nem sempre as coisas são como achamos ser ou parecem ser. Em javascript isso é bastante verdadeiro. Temos de conhecer a fundo a linguagem se quisermos escrever códigos limpo e seguro. Espero que tenham gostado.


