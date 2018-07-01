---
layout: post
title: My Introduction to ipyleaflet Jupyter Widget 
tags: jupyter maps gis learning
---

Recently I had a project were I need to plot locations on a map, the data was already in geopandas and I needed to add basemaps to the background of the plots to add context. 

One of the libraries mentioned at the March Tripython meeting was [ipyleaflet](https://github.com/jupyter-widgets/ipyleaflet), so I gave it a try.

Ipyleaflet is a widget for jupyter that allows easy embedding of [leaflet.js](https://leafletjs.com/) maps. The maps support basemaps, polygons, markers, layers, and nearly a dozen more mapping features including animations and video overlay. 

I have posted a [demo notebook](https://github.com/gnfrazier/geopandas-demo/blob/master/ipyleaflet.ipynb) with a quick example of pulling in locations from the google places API, then plotting them on the map. One small bummer is that it does not support different colored markers yet, so I used a circle for the second marker, preventing the use of the super cool cluster marker feature.  

In general, I found ipyleaflet to be easy to get started with a basemap and a few plots, then powerfully extend with shapely and geopandas to handle the data and polygon control.

Additional map controls, such as the ability to interactively draw shapes in the map itself, give leaflet widgets many of the same features as larger gis libraries. Add in the ability to  move markers and control layers pan, zoom and manipulate as well as render in a split screen... I am hooked.

### Additional Reading

[Ipyleaflet docs](https://ipyleaflet.readthedocs.io/en/latest/index.html)  
[Leaflet.js homepage](https://leafletjs.com/)  
[Leaflet out of the box base map catalog](https://leaflet-extras.github.io/leaflet-providers/preview/)  
