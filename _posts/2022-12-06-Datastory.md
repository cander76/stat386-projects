---
layout: post
title:  "The Best Part of Data: Exploring it!"
date:   2022-11-16
author: Caitlyn Anderson
description: My spin exploratory data analysis. This EDA focuses on the Top 64 Movies of all Time.
image: /assets/images/cover.jpg
---

## Introduction

I used to think that numbers and words could never go together. Math classes are strictly numbers and English classes are strictly words (which, as someone who is not great at using her words, is why I would always gravitate and love math classes). However, throughout my time studying statistics at BYU, I have realized that numbers (data) can tell you so much about a situation, and analysis of data is super insightful. Learning how to approach data and takeaway key main ideas is no easy task, but in this post, I will talk about the approach I took with some data that I webscraped!

## The data

The first step to telling a compelling data story is to collect the data! I performed a web scrape on a dataset from Rotten Tomatoes to see what the top movies of all time are (not limited to a certain genre). Through the process of web scraping, I collected the data from that website, specifically the movie titles, rankings, ratings, genres, runtimes and star ratings. I then cleaned the data and put it all together into a data frame to allow for easy analysis and plotting. The link to my blog post in which I talk about the process of scraping and cleaning this particular dataset can be found [here](https://cander76.github.io/stat386-projects/2022/10/16/webscraping.html) Not only was I interested in seeing how the top movies of all time compare to mine, I was also hoping to see if certain genres, years and ratings (G,PG,PG-13, R, etc) have a correlation to the star ratings they are given.

So with all the data cleaning and wrangling, I decided to tell a story of how genres and ratings play into the star ratings on IMDB. Through this graphic, you can see that Dramas dominate the top 64 list of movies according to IMDB, while Biographies and Documentaries do not. There seems to be an even distribution of ratings for the most part, though PG-13 movies do not seem to be as prominent as the others.

I also chose to include a graphic showing the star ratings throughout the years. Although it seems the star ratings have been pretty constant over time, we see that there has been a slight decrease in ratings since 2000. We can also see the highest rated movies (outliers) all occurred before 1980. So from these we know that throughout time, movie ratings have slightly gone down, and Drama seems to be the most popular genre (according to IMDB)

The link to my GitHub repository that includes the full code for this project and the csv file of the dataset can be found [here](https://github.com/cander76/Webscraping)
