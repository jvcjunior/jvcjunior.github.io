---
layout: post
title:  "Entendendo o this em Javascript"
date:   2016-02-02 10:15:00
categories: github javascript this keyword
tags: github javascript this keyword
published: false
---

Fala galera, beleza? Esse post fala sobre um carinha muito pouco compreendido no mundo JS que é o ´this´. Vou tentar explanar um pouco sobre esse cara e vou procurar fazer isso da maneira mais fácil possível. 

## Motivação?

Para quem está acostumado a programar em linguagens como Java ou C#, sabe que a palavra this se refere a instância atual do objeto. Logo, cada instância criada tem o seu this que pode ser acessado dentro da mesma. A função da palavra-chave this comporta-se um pouco diferente em Javascript se comparado com outras linguagens. Também possui algumas diferenças entre o modo estrito e o modo não estrito. Na maior parte das vezes, o valor this é determinado pela forma como você chama a função. Essa diferença deixa muita gente confusa. Eu mesmo, as vezes, me pego questionando qual o seu valor em determinados pontos do código. Mas uma coisa é certa, é tudo questão de regras. 

## Motivação?
