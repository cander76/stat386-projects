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

![Figure](https://github.com/cander76/stat386-projects/raw/main/assets/images/graphing.jpg)


# One time step:

The first thing you want to be sure of is that you have the ggplot package installed into RStudio. The ggplot package is in the tidyverse library. If you do not already have this downloaded, you will need to run the command:

```install.packages(‘tidyverse’)```

in RStudio. If you already have the package installed, each time you run R, you will need to load the package by running the command:

```library(tidyverse)```

This will load the ggplot package and you are ready to start visualizing!

# Datasets

Of course, when graphing data, you are going to need a dataset to manipulate and get to the desired output. Ggplot only takes in datasets that are in the form of a data frame. In this example, we will be using the mtcars dataset that is already installed in the tidyverse. There are many datasets that you can install into R, or you can scrape your own data, but that is another lesson for another time. We can view the components of this specific mtcars dataset by using the command: 

```?mtcars```

Running this command will pull up this menu:

![Figure](https://github.com/cander76/stat386-projects/raw/main/assets/images/mtcars.png)

With this, we can see all of the different variables we can use to put into our plots. In this beginner’s guide, we are only going to make a simple plot using only 3 of the variables.

# Basic Format of a ggplot Statement

With any dataset, the way to format a ggplot command is to call the ggplot function, input the dataset, and choose the variables you would like to visualize using the “mapping = aes” command. You can then add the type of graph you would like. There are many options for this including but not limited to:

-geom_point (scatter plot)

-geom_bar(bar graph)

-geom_smooth (adds line to graph)

-geom_line (for continuous variables)

More examples of formatting can be found [here](https://nyu-cdsc.github.io/learningr/assets/data-visualization-2.1.pdf)

When you put this all together, this is what the basic format should look like:

```ggplot(data = <DATASET>, mapping = aes(x = <DESIRED X VARIABLE>, y = <DESIRED Y VARIABLE>)) + geom_<YOUR CHOICE>```

# Real Example

Now let's do a real example from the mtcars dataset! For this example, I am interested in seeing the correlations between 3 variables: weight, mpg, and transmission. To add a 3rd variable, I am going to add “color” to the aes argument and make it discrete so I can easily change the legend. I am also going to add labels to my plot using the labs() command. More of what you can add to this argument can be found using the command 

```?labs```

This is what my code looks like:

```ggplot(data = mtcars, mapping = aes(x = wt, y = mpg, color = factor(am))) + geom_point() + scale_color_discrete(name = 'Transmission', labels = c('Automatic', 'Manual')) + labs(x = 'Weight (1000 lbs)', y = 'Miles per Gallon', title = 'Cars')```

This code will result in the plot:

![Figure](https://github.com/cander76/stat386-projects/raw/main/assets/images/GGplot.png)

With this basic knowledge of ggplot, you are ready to go out and visualize your very own datasets. Though these examples may seem simple, they are the building blocks to data visualization. Thanks for reading, leave a comment saying how you will use ggplot!

