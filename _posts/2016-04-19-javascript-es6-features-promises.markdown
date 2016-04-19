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

I became familiar with the idea of promises because of AngularJS. At the beginning I spentsome time to undestand this concept and once I did that I started to use in my applications. It is very easy to use and very helpful.

## Promises
Promises are a pattern that helps with one particular kind of asynchronous programming: functions (or methods) that return their results asynchronously. To implement such a function, you return a promise, an object that is a placeholder for the result. The caller of the function registers callbacks with the promise to be notified once the result has been computed. The function sends the result via the promise.

1. Promises are objects which store information about whether or not those events have happened yet, and if they have, what their outcome is.
2. Promises are created inside of asynchronous functions (those which might not return a response until later), and then returned. When an event happens, the asynchronous function will update the promise to notify the outside world.
3. Promises don’t handle anything by default, but success and failure handlers are attached later.
4. Promises can only represent one event – they are either successful once, or failed once.




http://jamesknelson.com/grokking-es6-promises-the-four-functions-you-need-to-avoid-callback-hell/
http://www.2ality.com/2014/10/es6-promises-api.html
