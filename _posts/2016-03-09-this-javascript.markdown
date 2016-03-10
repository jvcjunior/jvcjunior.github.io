---
layout: post
title:  "Entendendo o this em Javascript"
date:   2016-02-02 10:15:00
categories: github javascript this keyword
tags: github javascript this keyword
published: true
---

Fala galera, beleza? Esse post fala sobre um carinha muito pouco compreendido no mundo JS que é o ´this´. Vou tentar explanar um pouco sobre esse cara e vou procurar fazer isso da maneira mais fácil possível. 

## Motivação?

Para quem está acostumado a programar em linguagens como Java ou C#, sabe que a palavra `this` se refere a instância atual do objeto. Logo, cada instância criada tem o seu `this` que pode ser acessado dentro da mesma. A função da palavra-chave `this` comporta-se um pouco diferente em Javascript se comparado com outras linguagens. Também possui algumas diferenças entre o modo estrito e o modo não estrito. Na maior parte das vezes, o valor `this` é determinado pela forma como você chama a função. Essa diferença deixa muita gente confusa. Eu mesmo, as vezes, me pego questionando qual o seu valor em determinados pontos do código. Mas uma coisa é certa, é tudo questão de regras. 

## Nada além de regras

Toda função JavaScript, ao ser executada, gera uma associação do objeto criado pelo interpretador através da palavra reservada `this`. A especificação da ECMAScript chama isso de `ThisBinding`, um evento que acontece toda vez que um código JavaScript é executado e um novo contexto de execução é estabelecido. Na maioria das vezes o valor do `this` é determinado por como a funcção foi chamada. Não pode ser setado por atribuição em tempo de execução e pode ter um valor diferente em cada chamada da função. Por isso vamos analisar as regrqas por trás da identificação do `this` no código. Vamos mostrar na ordem de prioridade. Algumas regras tem prioridade em função das outras e iremos listar da maior para menor. 

### Quando a função é chamada usando `new`
A primeira regra com a a maior prioridade é quando uma função é chamada usando o `new binding`.
O que isso significa? Vamos ver um exemplo: 
```javascript
function Pessoa(nome) {
    this.nome = nome;
}
 
var pessoa1 = new Pessoa("Valter Júnior");
console.log(pessoa1.nome); // Valter Júnior
```

Quando o operador `new` é colocado na frente da chamada de uma função então um novo objeto é criado e atribuido sua instância para o `this`. O novo objeto criado tem como `prototype` uma refência para `Pessoa.prototype` o que nesse caso é um objeto vazio. Se a função não retornar nada explicitamente então o uma referência para o `this` será retornada. 

### `binding` Explícito

O `binding` explícito força o `this` a referencciar o objeto especificado.Vamos ver um exemplo:
```javascript
function teste() {
    console.log("Olá " + this.name );
}
 
var pessoa1 = {
    name: "Valter"
};
 
var pessoa2 = {
    name: "Júnior"
};
 
teste.call(pessoa1); // Olá Valter
teste.apply(pessoa2); // Olá Júnior
```
Conseguiu perceber?  Com o .call e o .apply podemos atribuir ao `this` uma referência ao objeto que queremos em qualquer chamada de função(com exceção de funções que usam ´hard binding´) .
Notem a especificação do apply e do call:
```javascript
Function.prototype.apply(thisArg, [argsArray])
Function.prototype.call(thisArg[, arg1[, arg2[, …]]])
```
A diferença entre os dois é que o apply permite que a função seja executada com um array de parâmetros enquanto o call requer que os parâmetros sejam listados explicitamente. 

### `hard binding`
### `binding` implícito
### Contexto Global (`default binding`)

No contexto global de execução(fora de qualquer função), `this` se refere ao objeto global, quer estejamos trabalhando em `strict mode` quer não. 
Considere por exemplo o código abaixo: 

```javascript
console.log(this.document === document); // true
// Nos web browsers, o objeto `window` é também o objeto global:
console.log(this === window); // true
this.a = 37;
console.log(window.a); // 37
```



