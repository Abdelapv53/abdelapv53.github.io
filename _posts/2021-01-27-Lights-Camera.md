---
layout: post
title: Lights, Camera, Disappointment
subtitle: What are the chances of watching a bad movie given the genre?
gh-badge: [star, fork, follow]
tags: [projects, movies]
comments: true
---

I was watching a movie the other day. All of a sudden, I found myself scrolling thru facebook looking for the next corgi post that I could give my _heart react_ to, completely forgetting about the movie and how I got around watching it in the first place. Was it due to my short attention span? Was it the adorable corgis? Or, was it because **the movie just really... sucked?**


![dataset](/assets/img/GettyImages-944229620.jpg)

So, for my first actual project, I decided to do my research on the [IMDb Dataset](https://datasets.imdbws.com/) and started with the question "How is movie genre related with average ratings?"

## The Data:

The dataset is broad and extremely detailed. It contains general information and some additional measures and descriptors. Luckily, I did not have to do a lot of data cleaning . In total there was 85000+ unique observations; details of movies from all over the world with the earliest recorded movie dating 1888 (["Roundhay Garden Scene"](https://www.imdb.com/title/tt0392728/)) up to the most recent ones to date.

![dataset](/assets/img/The data.jpg)

Since it was a considerably large dataset and also to produce more specific results, I decided to shrink the dataset into just the movies produced in the USA and managed to return with a quarter of the original amount. To further make it a bit simpler, I've also only included the top 5 most watched movie genres: Drama, Action, Comedy, Horror and Sci-Fi.

## The Tests:

I figured a t-test would be appropriate to see if the sample mean(genre) is equal to the total population mean(movies made in usa). With the population mean of 5.56 my Null and Alternative hypotheses would look like this:

![Hypotheses](/assets/img/hypothesis.jpg)

I conducted the t-test and came up with the following p-values

![p-values](/assets/img/pvalues.jpg)

All of the p-values are extremely low even at a significance level of 0.001, which means the Null Hypothesis will be rejected and I will fail to reject my Alternative hypothesis stating that "The mean of all movies is not equal to the mean of all the movies when classified by genre"

I've Also decided to do a box plot to visualize the means of each movie category:

<iframe width="900" height="800" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/1.embed"></iframe>


Now that it has been established that "All movies are rated differently according to genre", I used crosstab to calculate for the conditional probability of each genre basically answering questions like "What are the chances of watching a Horror movie given that it's Good?". And to do that, I generalized my average votes into 3 different "Qualities"

![Quality](/assets/img/badokgood.jpg)

{: .box-note}
***Disclaimer:*** these are all flexible variables based on personal preference. I had to skew the ratings in a way so that it would make simpler categories.

![crosstab](/assets/img/crosstab.jpg)

By the looks of it, 51% of all horror movies (made in the us) are rated "Bad", 44% are "Okay" and about 5% will potentially leave you traumatized, **forever.**

## The Pies:

<iframe width="350" height="350" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/3.embed"></iframe> <iframe width="350" height="350" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/9.embed"></iframe><iframe width="350" height="350" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/14.embed"></iframe><iframe width="350" height="350" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/17.embed"></iframe><iframe width="350" height="350" frameborder="0" scrolling="no" src="//plotly.com/~AltruisticVigilante/20.embed"></iframe>

## The Conclusion:

The presented data tells information on how movie genres and average votes are related. I find it interesting how "Drama" is often rated high compared to "Horror". There is much information unaccounted for. Some data might even be too complex or too abstract to be measured or recorded. A perfect model to predict which kinds of movies is best recommended to a user at a given time. Building it seems difficult however, it's not impossible.
