---
title: Time Series!
author: Roxanne Stockard-Hicks
date: '2017-12-18'
slug: time-series
categories: []
tags: []
thumbnail: path/thumbnail.jpg
---

First again, we need to load the necessary packages:
library(Lahman)
library(ggplot2)
library(sqldf)

Pick the data we want, in this case number of home runs Babe Ruth made each year he played baseball:
 query<-"SELECT yearID,HR
 FROM Batting
 WHERE playerID='ruthba01'"

 result<-sqldf(query)
 
 Last, here is how to make a time series chart with this information:
 ggplot()+
   geom_point(data=result,aes(x=yearID,y=HR))+
   geom_line(data=result,aes(x=yearID,y=HR))+
   ggtitle("Ruths Homeruns")+
   xlab("Year")+
   ylab("Homeruns")