---
title: "Histograms!"
author: "Roxanne Stockard-Hicks
date: '2017-12-18'
slug: histograms
categories: [R, histograms]
tags: []
thumbnail: path/thumbnail.jpg
---

First, you need to load the necessary packages:

library(Lahman)
library(ggplot2)
library(sqldf)

Now, pick the parameter you'd like to look at, which here is weight for all players:

query<-"SELECT weight
 FROM Master"

 result<-sqldf(query)

Last, create a bar plot for frequency of all weights in the Lahman database:

ggplot()+
   geom_histogram(data=result,aes(x=weight),color="blue",fill="white",bins=50) +
   ggtitle("Body weight")