---
layout: post
title: Analytics Forward - An Unconference
tags: data conference 
---

This is my 3rd Analytics Forward. It is always a good conference, even more so now that I know so many people in the community. 

I attended several talks, here are my notes from the most inspiring.

### Data Visualization from Start to Production

Plotwatt smart meter

-   Widely diverse clients with a wide range of customers
-   Ability to quickly prototype dashboards for clients

Python on Ruby with Angular on top.  
Plotly graphing package  
    python
    R 
    Matlab

Plotly offline vs plotly online
    graph objects is the base viz type  
    Data elements is a list or dict 
    layout defines scale, axis etc

Base methodologies
    define the data list
    graph object.bar to define the bar chart
    can append more graph objects to that list to overlay the data 

Darksky weather API for forecasting

plot.ly/python  
    Dash for front end work. 

* * *

### How to present stats to non stats people

[Melinda Thielbar](https://www.twitter.com/mthielbar)

Tukeys Studentized Range 

-   Classic analysis is to run an Anova
-   Then do multiple comparisons test 

The Family-wise error - the chance of at least one false positive

Studentized Newman Kool  

-   Not as good avoiding false positive  

Tukey test is a difference against one number.

Newman Keuls, count the difference of means of the nearest means

Watch the sample size as it changes the validity of the test, make sure the test the use is valid for what you want to do. 

Max diff analysis  Stuff in the middle is harder  
Likert scale vs continuous data  
ordinal logistical regression  
parse out the individual differences from the subjects, mean.  
So if John's mean is 5, base his answers as differences from 5  

* * *

### How to transform a feed of transactional data in to the parameters of 'Dan', 'Steve', Joe.

What if we used a social network to define how those people are people.

Transactions have 2 actors  

-   The consumer
-   The bank

No but there is a longer chain

-   Consumer
-   Retailer  
-   Payment processor
-   bank 

For transaction data at banks there are a lot of attributes. Some of them are straight forward. Others are really obscure.

So do you need all those attributes, do they help you do better analysis? 

Summarize/Roll-Up transactions  

-   Distributions

    -   Min
    -   Max
    -   Mean
    -   Median

How about stratified distributions. Filter your data by a single attribute to create subsets.

Those attributes start to form your different groups of people. 

For date time you can make a time series 

-   Trend  
-   Recent Trend  
-   Seasonality  
-   Differences  
-   Outliers  
-   RFM  Recently Frequency and Monetary Value

**6 degrees of wikipedia  **

The metadata will Frequently give the links in the network that is the clue for how to group the subjects. 

Networks and Transactions can be summarized in identical ways.  

-   The nodes give a clue for how subjects can be linked. 
-   Start to use where people are in the network to determine their likely hood of creating a transactions.
-   Shortest path to a node is the measure of likelihood.
    -   IE, you buy bananas, person B buys bananas, person B bought apples, how likely are you to buy apples. 

* * *

### Keynote with [Mara Averick](https://www.twitter.com/dataandme/)

When applying what you learn you need buy-in from the stakeholders.  
    Dealing with world that is half in english, and half in squiggly is a skill.

data rectangling by Jenny Bryan

R markdown - Jupyter Notebooks 

Pool package in R - what is in python. 

* * *

### Indoor Position Systems

[Alice Broadhead](https://www.twitter.com/alicebroadhead/)

**Goals**

-   Indoor Navigation  
-   Optimize Store Layout  
     How to Optimize stores and where people are. 

Checkout Free Shopping  

**Methodologies ** 

-   Signal processing 
-   triangulation (angles) 
-   proximity 
-   fingerprinting

Fingerprinting  

-   Compare a baseline of signals to when there is  a new signal  

Ultrasound  

-   like a bat transmitter emits a ping, the listeners figure out the location  
-   used to quantify and measure the error in other systems  

WiFi and bluetooth  

-   Useful for everything but dead reckoning  
-   Usually combined with fingerprinting (mac address)  
-   BLE is more practical the scans are frequently updated
-   Mapping the entire spectrum and using fingerprinting is usually the best for wifi and BLE

UWB Ultra Wide Band  

-   wide band and short pulse
-   Low Transmission Power
-   Short pulses reduce multipath issues
-   At this point needs special transmitter

LIDAR  

-   used in self driving cars 
-   usually based on dead reckoning 
-   expensive at this point 

Visible light 

-   mobile phone app to track where it device is.  
-   The flicker from a fluorescent bulb is a UID  

Noise in the data  
Kalman Filter
Particle Filter

WiFi plus Compass  

-   Not only the earth's magnetic field, but steel in the building

* * *

### Too Many Bars

[Xan Gregg](https://www.twitter.com/xangregg/)

When too many categories Bar Charts frequently end up too crowded.

How can you display all the categories without losing the information. 

Frequently end up zooming in on only one portion of the data, throwing out the others. 

To avoid throwing out the others completely, The rest can be grouped into 'OTHER' but this will sometimes swamp the other bars, blowing out the scale. 

Focus plus Context - instead of layers  

-   Central element with labels
-   Additional data needs mouseover/hover to get the data.

Can you use a Treemap instead?  

-   Still focus and concept
-   Label the top 10 or so
-   Good because it gives a good feel for the whole picture
-   Minus is that it is a shift to area, a less good way to show differences.

Pack Bubbles  

-   See a lot in the media
-   More fun
-   Even harder to determine size
-   Packing leaves white spaces

Dot Plot  

-   Similar to bar Chart 

How about packed bars?  

-   Like a hybrid between bar and Treemap  
-   No info lost, still focus on the top 10  
-   Gives context for the whole spaces  
-   Can layer in heatmaps and gradients to add another dimension
-   Looks similar to stacked bar chart  
-   R packed bars  
-   Excel package  
-   D3  
-   Chubuk.js  

What about when the data is less skewed?  

-   On packed bars it is just a grid
-   No advantage to the display

Wrapped Bars  

-   Get to the bottom start at the next column
-   Also good for skewed data  
-   Less context, but still on the screen  

Piled Bars  

-   Little bit of 3d shading  
-   Small ones are close to the x axis  
-   Better with normal distribution  

Zvinca Plot  

-   Lots of noise  
-   Similar to a scatterplot  
-   Better with a normal Distribution  

More info on [XanGregg on Github](https://github.com/xangregg/)
