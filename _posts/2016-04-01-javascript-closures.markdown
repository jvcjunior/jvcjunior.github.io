---
layout: post
title:  "Javascript Closures"
date:   2016-04-01 10:15:00
categories: javascript closure
tags: javascript closure
published: false
---

Hey guys, I am going to start writing some posts in english and this will be the first one. I hope you can understand what I am trying to say and this post help you to understand this concept that for me was hard to understand but now I see it isn't so hard. 

### Definition

`Closure is when a function is able to remember and access its lexical scope even when that function is executing outside its lexical scope.`

Let's see some code to understand that definition:

```js
function foo() {
    var a = 2;
    function bar() {
        console.log( a ); // 2
    }
    bar();
}
foo();
```

