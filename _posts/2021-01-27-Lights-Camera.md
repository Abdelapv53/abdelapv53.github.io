---
layout: post
title: Lights, Camera, Disappointment
subtitle: How often are Horror movies _actually_ scary?
gh-badge: [star, fork, follow]
tags: [projects, movies]
comments: true
---

I was watching a movie the other day all of a sudden, i found myself scrolling thru facebook looking for the next corgi post that i could give my "heart react" to. Completely forgetting about the movie and/or why i watched it in the first place. was it because of my lack of attention span? was it the adorable corgis? or was it because **the movie just really sucked..?**

So for my first actual project i decided to do my research on the [IMDb dataset](https://datasets.imdbws.com/) and started with the question "How is movie genre related with average ratings?"

## The Data:

The Dataset is broad and extremely detailed. it contains general information and some additional measures and descriptors. i did not have to do a lot of data cleaning but in total there was 85000+ unique observations. details of movies from all over the world with the earliest recorded movie dating 1888 (["Roundhay Garden Scene"](https://www.imdb.com/title/tt0392728/) up to the most recent ones to date.

#Dataset pic

Since it was a considerably large dataset and also to produce more specific results. i decided to shrink the dataset into just the movies produced in the USA and managed to return with a quarter of the original amount. to further make it a bit simpler. i've only decided to include the top 5 most watched movie genres: Drama, Action, Comedy, Horror and Sci-Fi.

## The Tests:

I figured a t-test would be appropriate to see if the sample mean(genre) is equal to the total population mean(movies made in usa). with the population mean of 5.56 my Null and Alternative hypotheses would look like this:

#Null and Alt pic

I conducted the test and came up with the following p-values

#P-values pic

All of the p-values are extremely low even at a significance level of 0.001 which means the Null Hypothesis will be rejected and i will fail to reject my Alternative hypothesis stating that "The mean of all movies is not equal to the mean of all the movies when classified by genre"

I've Also decided to do a box plot to visualize the means of each movie category:

#plotly box plot

Now that it has been established that "All movies are rated differently according to genre" i used crosstab to calculate for the conditional probability of each genre basically answering questions like "What are the chances of watching a Horror movie given that it's Good?". and to do that. i generalized my average votes into 3 different "Qualities"

#Quality pic

{: .box-note}
***Disclaimer:*** these are all flexible variables based on personal preference. i had to simplify the ratings in a way that it would make more sense.

#Crosstab pic

and finally, some pie :)

#pie charts for every genre



