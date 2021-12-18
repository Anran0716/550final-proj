---
title: " Data collection and preprocessing"
date: 2021-12-18T15:34:30-04:00
published: true
tags: [python, Tweepy, TextBlob, matplotlib]
excerpt: "Collect and clean Twitter Data"
toc: true
toc_sticky: true
---

## Data collection
In the very first beginning,we loaded the Airbnb Listing data (from [InsideAirbnb][InsideAirbnb]) and cleaned the original dataset. To be more specific, we removed data that do not contain location information,then transformed datatype of certain fields(*e.g. price,host_response_rate*), and added new field `price_per_person` (*price_per_person=price/accommodates*) into our Airbnb dataset. Also, we loaded New York neighborhood data (from [NYC OpenData][NYC OpenData]), which served as a spatial reference for further analysis. (Hasa)

- See the code of [Pulling recent data](https://github.com/Anran0716/550final-proj/blob/main/code/Pull%20recent%20data.ipynb) and the [Pulling historical data](https://github.com/Anran0716/550final-proj/blob/main/code/Pull%20historical%20data.ipynb).

    
## Data Preprocessing
Below, we plot the histogram of Airbnb Price in New York,and found that most of Airbnb listings ranged from $60 to $169. (Hasa)


![distances-abandoned-cars]({{ site.url }}{{ site.baseurl }}/assets/images/overview_Twitter.PNG)

- See the code of [Data preprocessing](https://github.com/Anran0716/550final-proj/blob/main/code/data%20preprocessing.ipynb).
