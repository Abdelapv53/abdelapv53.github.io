---
layout: post
title: Using Tree Based Models to Calculate Tokyo AirBnB Prices
subtitle: How to get a comfier bang for your buck
gh-badge: [star, fork, follow]
tags: [projects, travel, tokyo]
comments: true
---

Travelling is something almost everyone wishes they would've done when they we're younger. And if you ask my Aunt Lucy she would tell you that she "didn't have time" or she "was afraid to go alone".. But mainly, apparently it was **too expensive**. But What if it didn't have to be?
Within the recent boom of 3rd party apps offering a cheaper alternative to taxi rides and pricey hotels, AirBnB has remained on the top contender of the list. Allowing 'hosts' to utilize their dusty guest rooms and turn it into a profit the website has increasingly become popular amongst backpackers and travelers on a budget.
I myself got curious on which aspects of an AirBnB contributes towards the price. I was also motivated by my secret goal of finding a potential candidate for my next vacation.

![Japan](/assets/img/fuji.jpg)

## The Data:

I decided to pull (["AirBnB listings from Tokyo, Kantō, Japan"](http://insideairbnb.com/get-the-data.html). A week's worth of scraped data from December-30-2020 to January-05-2021. It contained a total of 10859 observations and 73 features.
The features contained Basic listing features (number of beds, maximum guests & amenities) and Host information(URLs, host being 'Superhost', etc). Data cleaning wasn't too hard, the data came in clean as it is. The main challenge i had was to pick which features to use and how to feature engineer them.


## The Models:

After splitting the data and Identifying the baseline. Since it's a regression problem, I primarily used a Ridge Regression model and then began on preparing the other two tree based models; RandomForestRegressor and XGBRegressor.
![RFRegressor](/assets/img/MetricsRFU2.JPG)
20 minutes of hyperparameter tuning later the Random Forest Regressor performed best among the three models.

## Communicating Results:

Based on the dataset. The two most distinguishing factors of how much the price of an AirBnB would be are The number of bedrooms and the number of guests that could be accommodated.

![Partialdependancy](/assets/img/pdpu2.JPG)

Another Thing that i got around asking myself was "Is location key? When it comes to AirBnB prices?"

<iframe width="900" height="800" frameborder="0" scrolling="yes" src="//plotly.com/~AltruisticVigilante/39.embed"></iframe>

I didn't want to overcrowd my datapoints so i only took a look at 200 observations and focused on low budget rentals ranging from 2000-16000JPY (Roughly $20-$150)
The short answer it yes, Location does matter. However it's not as impactful as the room type and ofcourse the aforementioned accommodation capacity and number of beds. I also noticed that most of these listings could have been established businesses even before AirBnB since most of the appartment type listings are clustered together.

In the end, My model did not have enough data to predict prices with pinpoint accuracy. Another factor could possibly be because prices are manually set by the host. AirBnB recommends a price range but the host has the final say on how much the property is going to cost per night.
