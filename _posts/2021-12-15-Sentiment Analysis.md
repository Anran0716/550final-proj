---
title: "Sentiment Analysis"
date: 2021-12-18
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Sentiment and emotional changes of people's atittude towards COVID vaccines"
hv-loader:
  hv-chart-1: ["charts/senti_month_line.html"] 
  hv-chart-2: ["charts/by_senti_bar.html"] 
  hv-chart-3: ["charts/emo_month_line.html"] 
toc: true
toc_sticky: true
---

This post will show examples of embedding interactive charts produced using [Altair](https://altair-viz.github.io) and [Hvplot](https://hvplot.pyviz.org/). (Hasa)

## Sentiment type

Below is a chart of the incidence of measles since 1928 for the 50 US states.(Hasa)

<div id="hv-chart-1"></div>

<div id="hv-chart-2"></div>


## Emotional type

Lastly, the measles incidence produced using the HvPlot package:(Hasa)

![emotional_tree]({{ site.url }}{{ site.baseurl }}/assets/images/emotional_tree.png)

<div id="hv-chart-3"></div>

- See the code for [Sentiment Analysis](https://github.com/Anran0716/550final-proj/blob/main/code/Sentiment%20analysis.ipynb).

