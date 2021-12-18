---
title: " Data collection and preprocessing"
date: 2019-12-11T15:34:30-04:00
published: true
tags: [python, Tweepy, TextBlob, matplotlib]
excerpt: "Collect and clean Twitter Data"
toc: true
toc_sticky: true
---

## Data collection
In the very first beginning,we loaded the Airbnb Listing data (from [InsideAirbnb][InsideAirbnb]) and cleaned the original dataset. To be more specific, we removed data that do not contain location information,then transformed datatype of certain fields(*e.g. price,host_response_rate*), and added new field `price_per_person` (*price_per_person=price/accommodates*) into our Airbnb dataset. Also, we loaded New York neighborhood data (from [NYC OpenData][NYC OpenData]), which served as a spatial reference for further analysis. (Hasa)

See the [lecture 9B slides](https://github.com/Anran0716/550final-proj/blob/main/code/Pull%20data%20by%20Kelly.ipynb) and the [lecture 10A slides](https://musa-550-fall-2021.github.io/slides/lecture-10A.html) for the code that produced these plots.


[InsideAirbnb]: http://insideairbnb.com/beijing/?neighbourhood=&filterEntireHomes=false&filterHighlyAvailable=false&filterRecentReviews=false&filterMultiListings=false
[NYC OpenData]: https://opendata.cityofnewyork.us/

    
## Data Preprocessing
Below, we plot the histogram of Airbnb Price in New York,and found that most of Airbnb listings ranged from $60 to $169. (Hasa)

add pictures here
![distances-abandoned-cars]({{ site.url }}{{ site.baseurl }}/assets/images/distance_to_abandoned_cars.png)

![histofprice](https://raw.githubusercontent.com/liziqun/MUSA620_Final_Project/master/assets/images/hist.png)

In terms of the average price by neighbourhood group, the Manhattan and Brooklin is much higher than Queens, Staten Island and Bronx, which explains why there are more Airbnbs in these two areas.  

![boxprice](https://raw.githubusercontent.com/liziqun/MUSA620_Final_Project/master/assets/images/box.png)

Is Airbnb price and the number of Reviews per month related with each other? The following figure tells us that the more reviews there are, the lower the price of the Airbnb might be, which means that cheaper Airbnb seems to have higher occupancy rate. Besides, the price of entire home is much higher than private room.  

![scatter](https://raw.githubusercontent.com/liziqun/MUSA620_Final_Project/master/assets/images/scatter_price_reviews.png)

Then, we also explored the relationship between `host_year` (the year that host opened the Airbnb) and the count of different Airbnb types.There is a general upward trend of new Airbnb listings, and both of the entire apt and private room seems to have a absolute big market share. Besides, an interesting finding is that the private room seems to have become a more popular chioce than the entire home for Airbnb host since 2015.   

![linecount](https://raw.githubusercontent.com/liziqun/MUSA620_Final_Project/master/assets/images/line_count.png)
