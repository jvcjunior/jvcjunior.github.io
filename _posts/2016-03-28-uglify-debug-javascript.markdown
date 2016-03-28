---
layout: post
title:  "Uglify para automaticamente remover mensagens de `debug`"
date:   2016-03-14 10:15:00
categories: github javascript gulp uglify debug console
tags: github javascript gulp uglify debug console
published: false
---

Fala galerinha, tranquilidade? Vou deixar um pouco o assunto do `this` do javascript de lado e falar agora sobre uma técnica bem interessante. As vezes queremos incluir alguns `console.log` enquanto estamos desenvolvendo a nossa aplicação. A maioria deles será removido antes do deployment, mas nem sempre é conveniente remover todos. Existem mensagens úteis que nos ajudam a identificar o que está acontecendo, como mensagens de log em requisições AJAX ou inicialização de módulos. Se removermos todas essas declarações e um bug é descoberto no código de produção, você terá de colocá-los de volta no lugar pra analisar o que está acontecendo. Certamente isso não é muito legal, não muito DRY(Don't repeat yourself)

http://web.archive.org/web/20141115053409/http://jstarrdewar.com/blog/2013/02/28/use-uglify-to-automatically-strip-debug-messages-from-your-javascript/

## Motivação
