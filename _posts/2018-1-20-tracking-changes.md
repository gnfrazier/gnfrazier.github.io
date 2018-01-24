---
layout: post
title: Tracking Changes
tags: jekyll github-pages linter
---

As notes for my self I am [tracking changes](/changes/) that I make to the css, \_config.yml and other files. While I could probably unravel them using github, if I choose to move to a new theme it will probably come in handy to have docs in a more readable format.

Plus I got to experience my first Jekyll build failure while working on the page. This nice alert email delivered to my inbox:

> The page build failed for the `master` branch with the following error:
>
> Page build failed. For more information, see [https://help.github.com/articles/troubleshooting-github-pages-builds/.](https://help.github.com/articles/troubleshooting-github-pages-builds/)
>
> For information on troubleshooting Jekyll see:
>
> <https://help.github.com/articles/troubleshooting-jekyll-builds>
>
> If you have any questions you can contact us by replying to this email.

The issues were minor, and ones a better linter for Markdown would have caught. I closed a set of quotes that started with /" with /' and I had used the _includes_ methods method wrong.

I added [linter-markdown](https://github.com/AtomLinter/linter-markdown "GitHub - linter-markdown") to my Atom packages. Hopefully it will catch the next error.

Yay for learning early!
