---
layout: page
title: Quick Modifications to Jekyllnow
permalink: /changes/
youtubeId: 2MsN8gpT6jY
vimeoId: 160580156
---

[Jekyllnow](https://github.com/barryclark/jekyll-now "GitHub - Jekyllnow") is a popular theme for Jekyll and GitHub pages. I like it because of its simplicity and sparse default layout. Here are the customizations I have applied. 

* * *

#### Center

Center an image or block of text. 
HTML to use inside markdown

```html
<div class="img_center">
Item to center
</div>
```

Add to style.scss 

```css
.img_center{
  text-align: center;
}
```

Append to the existing Kramdown block of \_config.yml

```yaml
kramdown:
  parse_block_html: true
```

Requisite [stackoverflow](https://stackoverflow.com/questions/39021630/kramdown-how-can-i-set-the-location-of-the-image "stackoverflow - kramdown how can I..") reference. 

* * *

#### Embed Videos

**YouTube**  
Create a HTML file called youtube.html in your includes file.

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ include.id }}" frameborder="0" allowfullscreen></iframe>
```

In the page or post's front matter:

```markdown
---
youtubeId: 2MsN8gpT6jY
---
```

In the body where you want the video use:  

{% highlight html %} {% raw %} {% include youtube.html id=page.youtubeId %} {% endraw %} {% endhighlight %}

**Vimeo**  
Create another HTML file called vimeo.html in your includes file.

```html
<iframe src="https://player.vimeo.com/video/{{ include.id }}" width="500" height="281" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
```

In the page or post's front matter:

```markdown
---
vimeoId: 160580156
---
```

In markdown use:  

{% highlight html %} {% raw %}{% include vimeo.html id=page.vimeoId %}{% endraw %} {% endhighlight %}

Credit to [Adam Harris](http://www.adamwadeharris.com/how-to-easily-embed-youtube-videos-in-jekyll-sites-without-a-plugin/ "AdamWadeHarris.com - how to easily embed...")

* * *

#### Syntax Highlighting to a Dark theme

From [Pygments CSS Themes](http://jwarby.github.io/jekyll-pygments-themes/languages/python.html "GitHub - Jwarby Pygments Themes") download a css file, add it to the \_sass directory, then rename it to \_name.scss. 

In the style.scss file, change:

```css
@import "highlights";
```

To:

```css
@import "name";
```

I selected monokai, it is the closest to the One Dark theme I use for Atom.

* * *

### Additional Reading

[GitHub Pages Compatible Plugins](https://help.github.com/articles/configuring-jekyll-plugins/ "GitHub Help - Configuring Jekyll Plugins")
