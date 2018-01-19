---
layout: page
title: Quick Modifications to Jekyllnow
permalink: /changes/
---

[Jekyllnow](https://github.com/barryclark/jekyll-now "GitHub - Jekyllnow") is a popular theme for Jekyll and GitHub pages. I like it because of its simplicity and sparse default layout. Here are the customizations I have applied. 

***

#### Center 
Center an image or block of text. 
HTML to use inside markdown
``` html 
<div class="img_center">
Item to center
</div>
```

Add to style.scss 
``` css
.img_center{
  text-align: center;
}
```

Append to the existing Kramdown block of _config.yml
``` yml
kramdown:
  parse_block_html: true
```

Requisite [stackoverflow](https://stackoverflow.com/questions/39021630/kramdown-how-can-i-set-the-location-of-the-image "stackoverflow - kramdown how can I..') reference. 

***
#### Embed YouTube Videos
Create a HTML file called youtube.html in your includes file.
``` HTML
<iframe width="560" height="315" src="https://www.youtube.com/embed/{{ include.id }}" frameborder="0" allowfullscreen></iframe>
```
In markdown use:
``` Markdown
{% include youtubePlayer.html id=page.youtubeId %}
```
Credit to [Adam Harris](http://www.adamwadeharris.com/how-to-easily-embed-youtube-videos-in-jekyll-sites-without-a-plugin/ "AdamWadeHarris.com - how to easily embed...")

***

