---
title: Scatterplots!
author: Roxanne Stockard-Hicks
date: '2017-12-18'
slug: scatterplots
categories: []
tags: []
thumbnail: path/thumbnail.jpg
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(collapse = TRUE)
library(ggplot2)
```
####Setup
First, let's set up some randomized data points:

```{r}
x<-rnorm(100,5,2)
y<-rnorm(100,2*x+1,2)

x
```

```{r}
y
```
####Progress
Now let's make the data frame:

```{r}
df<-data.frame(x,y)

df
```

####Results!
Finally, the scatterplot!

```{r}
ggplot()+
geom_point(data=df,aes(x,y))
```

