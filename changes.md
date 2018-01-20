---
layout: page
title: Quick Modifications to Jekyllnow
permalink: /changes/
youtubeId: 2MsN8gpT6jY
vimeoId: 160580156
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
``` yaml
kramdown:
  parse_block_html: true
```

Requisite [stackoverflow](https://stackoverflow.com/questions/39021630/kramdown-how-can-i-set-the-location-of-the-image "stackoverflow - kramdown how can I..") reference. 

***


