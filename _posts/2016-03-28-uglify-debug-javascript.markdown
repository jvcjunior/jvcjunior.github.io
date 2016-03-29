---
layout: post
title:  "Uglify para automaticamente remover mensagens de `debug`"
date:   2016-03-14 10:15:00
categories: github javascript gulp uglify debug console
tags: github javascript gulp uglify debug console
published: false
---

http://web.archive.org/web/20141115053409/http://jstarrdewar.com/blog/2013/02/28/use-uglify-to-automatically-strip-debug-messages-from-your-javascript/

http://elijahmanor.com/grunt-away-those-pesky-console-log-statements/

Fala galerinha, tranquilidade? Vou deixar um pouco o assunto do `this` do javascript de lado e falar agora sobre uma técnica bem interessante. As vezes queremos incluir alguns `console.log` enquanto estamos desenvolvendo a nossa aplicação. A maioria deles será removido antes do deployment, mas nem sempre é conveniente remover todos. Existem mensagens úteis que nos ajudam a identificar o que está acontecendo, como mensagens de log em requisições AJAX ou inicialização de módulos. Se removermos todas essas declarações e um bug é descoberto no código de produção, você terá de colocá-los de volta no lugar pra analisar o que está acontecendo. Certamente isso não é muito legal, não muito DRY(Don't repeat yourself)

Claro que você poderia deixar as declarações `console.log` no código. Mas existem alguns problemas com isso. 

1. É constrangedor ter logs no console de sua aplicação 
2. Pode influenciar a performance da aplicação
3. Pode causar alguns bugs no IE 8/9 quando o painel de ferramentas de desenvolvedor não está aberto

Se na sua aplicação existe minificação(O que eu recomendo fortemente), o UglifyJS pode nos fornecer uma solução para esse problema. O 'pulo do gato' aqui é que você pode definir constants enquando minifica. Por exemplo: 

```js
uglifyjs --define DEBUG=false "main.js" > "main.min.js"
```

