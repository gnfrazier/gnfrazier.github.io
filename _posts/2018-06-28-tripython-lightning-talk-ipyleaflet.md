---
layout: post
title: Lightning Talk: Displaying Maps in Jupyter with iPyleaflet 
tags: jupyter leaflet speaking-engagements
---

Last night at the [Tripython Meetup](https://www.meetup.com/tripython/events/251446010/) I gave a short demo of iPyleaflet, a Jupyter extension that quickly and easily displays base maps with geospatial features like points, point groups, isolines and shapes within your notebook.

For my demo we have a fictional business owner that wants to open a new location for their Yoga Studio chain, their data from other locations shows them that their preferred adjacencies are coffee shops and smoothie bars.

In the demo, I gave a quick run through rising the Google places API in python, then formatting the data to show in iPyleaflet. Then how layers and point markers could be quickly pushed into the map. 

The feedback from the group was generally good, however, there was one very valid comment from a GIS professional as to why I wouldn't use ARC GIS instead of coding it in Python. Honestly, I don't have a good answer except that in my real need use case all my data was already in a geo-pandas data frame, adding leaflet was only a few lines of code and i didn't have to learn a new platform along the way. 

#### Links and Additional Reading

[iPyleaflet Demo Notebook on Github](https://github.com/gnfrazier/geopandas-demo/blob/master/ipyleaflet.ipynb)  
[Tripython June 2018 Meetup](https://www.meetup.com/tripython/events/251446010/)    [iPyleaflet](https://github.com/jupyter-widgets/ipyleaflet)  
[iPyleaflet docs](https://ipyleaflet.readthedocs.io/en/latest/index.html)  
[Leaflet.js homepage](https://leafletjs.com/)  
[My Blog Post on iPyleafet](/2018-7-1-intro-to-ipyleaflet/ "gnfrazier.me - Review: iPyleaflet")
