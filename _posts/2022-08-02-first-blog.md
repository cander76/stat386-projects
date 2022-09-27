---
layout: post
title:  "Beginner's Guide to ggplot"
date:   2022-08-02
author: Caitlyn Anderson
description: The basics of data visualization in RStudio.
image: /assets/images/main photo.jpg
---

One of the most crucial parts of data science is data visualization. Sure, we can look at a large dataset and try to draw conclusions from just that, but it is much easier to be able to visualize what is happening in the data. This way we can easily pick out and identify obvious trends within the data. As for me, I am a visual learner, so it is always helpful to have some sort of graph to summarize data for me. One of the most efficient ways to carry out data visualization is by using ggplot in RStudio. 

# What is ggplot?

Ggplot is a data visualization package in the tidyverse library of R. This package takes in datasets and allows you to manipulate and graph them based on different areas of interest. It allows you to choose which specific variables of a data set you are interested in, and which type of plot you would like to see. In short, it gives the user a lot of control of what the plot should look like. I really love the freedom that comes with it because you can really take any data set (as long as it is in the form of a dataframe in R) and graph whatever you want with it!

# One time step:

The first thing you want to be sure of is that you have the ggplot package installed into RStudio. The ggplot package is in the tidyverse library. If you do not already have this downloaded, you will need to run the command:

```install.packages(‘tidyverse’)```

in RStudio. If you already have the package installed, each time you run R, you will need to load the package by running the command:

```library(tidyverse)```

This will load the ggplot package and you are ready to start visualizing!

# Datasets

Of course, when graphing data, you are going to need a dataset to manipulate and get to the desired output. Ggplot only takes in datasets that are in the form of a data frame. In this example, we will be using the mtcars dataset that is already installed in the tidyverse. There are many datasets that you can install into R, or you can scrape your own data, but that is another lesson for another time. We can view the components of this specific mtcars dataset by using the command: 

```?mtcars```

This will pull up this menu:





