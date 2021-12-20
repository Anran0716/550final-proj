---
title: "Topic modelling"
date: 2021-12-12
published: true
tags: [dataviz, wordcloud, hvplot]
excerpt: "Most frequent words in tweets about COVID-19 vaccines"
hv-loader:
  hv-chart-1: ["charts/top_words.html", "600"] 
toc: true
toc_sticky: true
---


## Wordcloud

[Text mining](https://en.wikipedia.org/wiki/Text_mining) is the process of extracting high-quality information from text. [Topic modeling](https://provalisresearch.com/blog/topic-modeling/) is also a form of text mining which employs statistical machine learning techniques to identify patterns in large amounts of text. It can take your huge collection of documents and group the words into clusters of words, identify topics, by a using process of similarity.   
In our project we use text mining and topic modeling, to identify the most recurring words from our dataset (all the tweets we have extracted between 1st Jan 2021 to 14th December  2021, and while excluding the most common words sets like ‘a’ ‘the’ ‘if’ etc.,). Based on this we are able to decipher – positive, negative and neutral words and mindsets associated with the vaccine. We further visualise this into 3 different word colour based on this interpretation. 

![wordcloud]({{ site.url }}{{ site.baseurl }}/assets/images/wordcloud.PNG)

## Top frequent words

To better understand which are the most used words in each month, we have visualised this in the form of a bar graph with a widget which can be used to change the month and the corresponding bar graph with 15 most used words of that month are revisualised.  


<div id="hv-chart-1"></div>

- See the [Topic modelling](https://github.com/Anran0716/550final-proj/blob/main/code/WordCloudBarGraph.ipynb) for the code that produced these plots.
