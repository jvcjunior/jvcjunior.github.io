---
layout: post
title:  "Compiled 'languages' x Interpreted 'languages'"
date:   2016-04-11 10:15:00
categories: javascript compiled languages interpreted
tags: javascript compiled languages interpreted
published: false
---

In the last days I've been studying javascript. Watching Kyle's Simpson advanced javascript course in pluralsight, I started to go deep into 
the differences between compiled languages and interpreted languages. I found some great stuff and would like to share with you. 

### Search for the truth
Let me explain my journey to find the differences between compiled languages and interpreted languages. It started when I was 
watching Kyle's course. In the course he spent a lot of time explaining how javascript engine works and the process of compilation 
of the language. When he said compilation I thought: 'Compilation? Is Javascript Compiled?' I was curious about that statement. 

Well, I decided to dig deep into this topic to find some answers. The first question I started to find an answer was: 

"Is javascript Compiled or Interpreted?". 

After some reading I realized that I would have to find the anwser to another question if I wanted to fully understand the answer to the 
first question I had. And this second question was: 

'What is the difference between Compiled 'languages' and Interpreted 'languages'?'.

### Big Question: Compiled 'languages' x Interpreted 'languages'
I don't know if you realized that I wrote languages in simple quotes. There's a reason for that. What I am trying to say is that there is no difference, because “compiled programming language” and “interpreted programming language” aren’t meaningful concepts. Any programming language, and I really mean any, can be interpreted or compiled. Thus, interpretation and compilation are implementation techniques, not attributes of languages.

Interpretation is a technique whereby another program, the interpreter, performs operations on behalf of the program being interpreted in order to run it. If you can imagine reading a program and doing what it says to do step-by-step, say on a piece of scratch paper, that’s just what an interpreter does as well. A common reason to interpret a program is that interpreters are relatively easy to write. Another reason is that an interpreter can monitor what a program tries to do as it runs, to enforce a policy, say, for security.

Compilation is a technique whereby a program written in one language (the “source language”) is translated into a program in another language (the “object language”), which hopefully means the same thing as the original program. While doing the translation, it is common for the compiler to also try to transform the program in ways that will make the object program faster (without changing its meaning!). A common reason to compile a program is that there’s some good way to run programs in the object language quickly and without the overhead of interpreting the source language along the way.

### Conclusion


