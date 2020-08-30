---
title: 'Data Visualisation and Analytics: Assignment 1'
author: "Hoang Diep_PHAN – ID: 30542707"
output: pdf_document
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE,eval=TRUE, error=TRUE)
library(tidyverse)
```

## Part A

*1. Provide a critical evaluation of Figure 1.*

The Figure 1 is a clear case of chart junk (Picture within the chart), bad data(the Y-axis) and low data density

*2. Provide a critical evaluation of Figure 2.*

The Figure 2 suffers from bad perception due to 3d rendering and low data density

*3. Provide a critical evaluation of Figure 3.*

Figure 3 suffers from chart junk with the dark grey background. 

*4. Provide a critical evaluation of Figure 4.*

Figure 4 suffers from bad data. There are some outlier

*5. Provide a critical evaluation of the text of the report.*

The text of the report tells nothing about the fact. It is easier for reader to be misleading.

*6. Discuss any positive aspects of the report*

The structure of report is good. It has three parts: introduction, analysis and conclusions. This is the only positive aspects that I can see from this report

## Part B

```{r}
# getwd()
a<-read.csv("electricitydata_assignment1.csv",TRUE,",")
library(ggplot2)
ggplot(data=a, mapping=aes(x=SolarRooftop))+geom_boxplot()
ggplot(data=a, mapping=aes(x=Price))+geom_boxplot()
g<-ggplot(data=a, mapping=aes(x=SolarRooftop,y=Price))+geom_point()
plot(g)
g+xlim(c(0,250))+ylim(0,150)
g1<-g+coord_cartesian(xlim=c(0,250),ylim=c(0,150))
plot(g1)
```
