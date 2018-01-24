---
layout: post
title: Code Macros in Atom Editor - Snippets
tags: atom-editor snippets macros workflow
---

Ever notice in Atom Editor that when you start typing common code constructions, it tries to auto-complete the rest of the block. For instance in Python if you start typing 'ifmain' it completes with:

```python
if __name__ == '__main__':
    main()
```

The [if main check](https://stackoverflow.com/questions/419163/what-does-if-name-main-do "StackOverflow - What does if \_\_main\_\_ do in Python?") is a frequently used construction, so Atom has it as a built in Macro or Snippet.

Unfortunately Atom does not have very many standard snippets for Markdown, but it is [easy to add your own](http://flight-manual.atom.io/using-atom/sections/snippets/ "Atom Editor Flight Manual - Snippets").  
To add a snippet to insert an image into Markdown:

From the edit menu select 'Snippets.'

  <img src="{{ site.baseurl }}/images/atom-edit-snippet.png" alt="Atom Editor - Edit Menu with Snippet Selected">

```css
'.text.md':
  'Image':
    'prefix': 'img'
    'body': '![$1]({{ site.baseurl }}/images/$2 "$3")'
```

1.  Scope[^1]
2.  Snippet Name 
3.  Text to trigger the snippet 
4.  The content of the snippet, for multiline code blocks use triple quotes.
    -   Note the $1, $2 and $3, set your tab order to populate the code block.

Here are some more I have found handy for Markdown.

Insert the Front Matter block for Jekyll:

{% highlight cson %} {% raw %}

'.text.md':
  'Post Front Matter':
    'prefix': 'post'
    'body': """

                    ---
                    layout: post
                    title: $1
                    --- 
                """

{% endraw %} {% endhighlight %}

**Footnotes**

[^1] Scope. Find the scope with the hotkeys control + shift + P then type scope. Use the first listing. 

### Additional Reading

[Atom Documentation - Snippets](http://flight-manual.atom.io/using-atom/sections/snippets/ "Atom Flight Manual - Snippets")

[Optional Parameters for Snippets](https://github.com/atom/snippets#optional-parameters "GitHub - Atom Editor Snippet Package Readme"): Style the type hint panel with CSS to add color highlights or custom text.
