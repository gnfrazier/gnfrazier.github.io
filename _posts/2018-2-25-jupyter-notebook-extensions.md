---
layout: post
title: Jupyter Notebooks with NBextensions
tags: python jupyter learning
---

<div class="img_center">
![Juypter NBextensions Tab]({{ site.baseurl }}/images/jupyter-nbextensions-tab-view.png "Jupyter Notebook with NBextensions Tab enabled. ")
</div>
While working on the post for [Jupyter Notebooks on Azure]({{ site.baseurl}}/jupyter-notebooks-on-azure/ "gnfrazier.me - Running Jupyter Notebooks on Azure") I noticed an NBextensions tab I had never noticed when running a local Jupyter Notebook server. 

Part of the reason my workflow in python is to experiment/build in Jupyter then transition to Atom for the final step is Atom Editors features like a code linter, snippets and tight Github integration. With NBextensions Autopep8, snippets and 3 dozen more features can be enabled directly in Jupyter. 

A quick google landed me on the [docs with install instructions](https://github.com/ipython-contrib/jupyter_contrib_nbextensions "GitHub - Jupyer Contrib NBextensions") page. Since I use conda I only had to do 2 steps, then restart my notebook server. 

One of the extensions that caught my eye is [Zen mode](http://www.damian.oquanta.info/posts/zen-mode-extension-for-the-ipython-notebook.html "Damian Oquanta - Zen Mode Extension for IPython"). A neat way to get away from the blank white background in Jupyter. 

### Additional Reading and links

[Jupyter Extensions - Documentation](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/ "Read the docs - Jupyter Extensions")

[Jupyter Extensions on GitHub](https://github.com/ipython-contrib/jupyter_contrib_nbextensions "GitHub.com - Jupyter NBextensions")

[Data Science Deconstructed - NB Extensions Review](http://datasciencedeconstructed.com/python/2016/11/22/install-jupyter-extensions.html "Data Science Deconstructed - Install Jupyter extensions")
