---
layout: post
title:  "Scrape Your Own Movies Dataset"
date:   2022-10-16
author: Caitlyn Anderson
description: Making a easy-to-read dataset in Pandas through webscraping and BeautifulSoup.
image: /assets/images/movie.jpg
---
 
# Introduction: What is the purpose of web scraping into Python?

Do you ever find yourself scrolling online, wishing information was presented to you in a more efficient way? Do you ever want certain data to be displayed to you immediately, but you have to scroll through a bunch of unnecessary information? Or maybe you want to easily interpret or visualize certain data, but you are restricted to what is given to you. I know I have experienced each of these frustrations throughout my life. Luckily, because of Python and some of the libraries it contains, we are able to take certain data from the internet and put it into a neat, easy-to-read data frame. With this knowledge, many doors are opened to data analysis and visualization. 

# What I chose to scrape

Recently in my Python class, I was tasked with making a dataframe displaying the top 88 heist movies of all time (according to Rotten Tomatoes). This had me curious to see what Rotten Tomatoes believed to be the top movies of all time (not limited to a certain genre). I found a webpage that displayed the top 64 movies of all time, found [here](https://www.imdb.com/list/ls033935095/). I am a big fan of movies, so I was really curious to see how my idea of top movies ever align with Rotten Tomatoes.

<img src="https://github.com/cander76/stat386-projects/raw/main/assets/images/popcorn.jpg" width="500" />

# Determining if scraping data is allowed

In python, the library used for making requests and using APIs is the requests library. When we use functions in this library, it is easy to tell what is and what is not okay to scrape. For this particular data, I used the code: 

```import requests```

```url = 'https://www.imdb.com/list/ls033935095/'```

```r = requests.get(url)```

After requesting the url, I was able to check the status to see if I was able to move forward with the web scrape.

```r.status_code```

If this code returns 200, that means everything went okay and we can continue.

# BeautifulSoup

Another key tool when it comes to webscraping is BeautifulSoup. This library can be loaded with the command:

```from bs4 import BeautifulSoup```

Once that is loaded, we can use it on the url we have with the command:

```soup = BeautifulSoup(r.content, "html.parser")```

This makes it easier to find tags and retrieve desired elements of a webpage. More information about BeautifulSoup can be found [here](https://nitratine.net/blog/post/python-beautiful-soup-basics-tutorial/#:~:text=Python%20Beautiful%20Soup%20Basics%20Tutorial%201%20Getting%20Your,3%20Using%20Beautiful%20Soup%20Parsing%20Your%20HTML%2FXML%20)

# Inspecting code from the webpage

Another way to pull information from a website is through looking at the raw code from the page itself. This may look intimidating at first, but once you figure out how to work it, it makes life so much easier! When I right clicked on my webpage of choice and hit “inspect” this is what I saw:

<img src="https://github.com/cander76/stat386-projects/raw/main/assets/images/genre.png" width="600" />

As you can see, it's pretty overwhelming and messy. However, lets say I am interested in extracting the genre from each film. I can then hover over a genre for one of the films, and the inspect feature will highlight the desired tags/class (as seen above). For genre, we see that “class = genre”. With this knowledge, I was able to use the find_all() function as seen below:

<img src="https://github.com/cander76/stat386-projects/raw/main/assets/images/genre python example.png" width="600" />

I repeated this process for each of my desire variables (title, rating, star rating, runtime, and year)

# Putting it all together

When building a pandas dataframe, it is important to first check that all of the variables are the same length. An example of this would be using the command: 

```len(Genre)```

which returns 64. Because all of my variables were of length 64, I was able to move forward with making my data frame using the command:

```df = pd.DataFrame({'Genre' : Genre})```

With this function, you can also add your other variables, separating them with commas. When I put all of my variables into a data frame, this is what some of my table looked like:

<img src="https://github.com/cander76/stat386-projects/raw/main/assets/images/table.png" width="600" />

Now, I can manipulate/visualize my data however I want to!

# Writing to a csv file

The last thing to do is write the data frame to a csv file. I did this by using the to_csv() function. I decided to name the file moviedata.csv and this is what my code looked like:

```df.to_csv("moviedata.csv", sep = '\t')```

# Conclusion

The point of this entire process is to be able to dive deep into data and see what we can learn from it. With this data set, I plan on performing an Exploratory Data Analysis (EDA) to gain insight on this information and share it with others! Come back again, and leave a comment about what you will webscrape in the future!

The link to my GitHub repository that includes the full code for this project and the csv file of the dataset can be found [here](https://github.com/cander76/Webscraping).
