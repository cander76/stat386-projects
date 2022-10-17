---
layout: post
title:  "Scrape Your Own Movies Dataset"
date:   2022-10-16
author: Caitlyn Anderson
description: Making a easy-to-read dataset in Pandas through webscraping and BeautifulSoup.
image: /assets/images/movie.jpg
---
 
# What is the purpose of web scraping into Python?

Do you ever find yourself scrolling online, wishing information was presented to you in a more efficient way? Do you ever want certain data to be displayed to you immediately, but you have to scroll through a bunch of unnecessary information? Or maybe you want to easily interpret or visualize certain data, but you are restricted to what is given to you. I know I have experienced each of these frustrations throughout my life. Luckily, because of Python and some of the libraries it contains, we are able to take certain data from the internet and put it into a neat, easy-to-read data frame. With this knowledge, many doors are opened to data analysis and visualization. 

# What I chose to scrape

Recently in my Python class, I was tasked with making a dataframe displaying the top 88 heist movies of all time (according to Rotten Tomatoes). This had me curious to see what Rotten Tomatoes believed to be the top movies of all time (not limited to a certain genre). I found a webpage that displayed the top 64 movies of all time, found [here](https://www.imdb.com/list/ls033935095/).

<img src="https://github.com/cander76/stat386-projects/raw/main/assets/images/popcorn.jpg" width="500" />

# Determining if scraping data is allowed

In python, the library used for making requests and using APIs is the requests library. When we use functions in this library, it is easy to tell what is and what is not okay to scrape. For this particular data, I used the code: 

```import requests```

```url = 'https://www.imdb.com/list/ls033935095/'```

```r = requests.get(url)```

After requesting the url, I was able to check the status to see if I was able to move forward with the web scrape.

```r.status_code```

If this code returns 200, that means everything went okay and we can continue.
