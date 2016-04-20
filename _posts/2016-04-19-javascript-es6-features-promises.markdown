---
layout: post
title:  "ES6 Features - Promises"
date:   2016-04-19 10:15:00
categories: javascript es6 promises
tags: javascript es6 promises
published: false
---

Javascript is envolving and a lot of new features were added to ECMAScript 6. ECMAScript 6 (ES6) was finalized in June 2015 and adds significant new syntax for writing complex applications. I`ll try to write something about each feature starting with Promises. 

### Introduction

I became familiar with the idea of promises because of AngularJS. At the beginning I spent some time to undestand this concept and once I did that I started to use in my applications. It is very easy to use and very helpful.

### Promises
Promises are a pattern that helps with one particular kind of asynchronous programming: functions (or methods) that return their results asynchronously. To implement such a function, you return a promise, an object that is a placeholder for the result. The caller of the function registers callbacks with the promise to be notified once the result has been computed. The function sends the result via the promise.

### First Promise
o construct a promise instance, use the Promise(..) constructor:

```js
var p = new Promise(function(resolve, reject) { ... });
```

As you can see, the Promise(..) constructor takes a single function (pr(..)), which is called immediately and receives two control functions as arguments, usually named resolve(..) and reject(..). They are used as:

1. If you call reject(..), the promise is rejected, and if any value is passed to reject(..), it is set as the reason for rejection.
2. If you call resolve(..) with no value, or any non-promise value, the promise is fulfilled.
3. If you call resolve(..) and pass another promise, this promise simply adopts the state -- whether immediate or eventual -- of the passed promise (either fulfillment or rejection).

Here's how you'd typically use a promise to refactor a callback-reliant function call. If you start out with an ajax(..) utility that expects to be able to call an error-first style callback:

```js
ajax("http://someurl", function handler(error,data){
    if (error) {/*handle ajax error*/}
    else {/*handle `data` success*/}
});
```

You can convert it to:

```js
function ajax(url) {
    return new Promise( function pr(resolve,reject){
        // make request, eventually call
        // either `resolve(..)` or `reject(..)`
    } );
}

// ..

ajax( "http://someurl" )
.then(function fulfilled(data){
        // handle `data` success
    },
    function rejected(errorReason){
        // handle ajax error reason
    }
);
```

Promises have a then(..) method that accepts one or two callback functions. The first function (if present) is treated as the handler to call if the promise is fulfilled successfully. The second function (if present) is treated as the handler to call if the promise is rejected explicitly, or if any error/exception is caught during resolution.

This is just an example of how you can use this powerfull tool of es6. There are more details about promises that I did'n talk about it. This is only an incentive for you to be curious and search more
