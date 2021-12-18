---
title: "Sentiment Analysis"
date: 2021-12-18
published: true
tags: [dataviz, altair, hvplot, holoviews]
excerpt: "Embedding interactive charts on static pages using Jekyll."
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

This was produced using Altair and embedded in this static web page. Note that you can also display Python code on this page:

```python
import altair as alt
alt.renderers.enable('notebook')
```

## Emotional type

Lastly, the measles incidence produced using the HvPlot package:(Hasa)

insert pylot here

<div id="hv-chart-3"></div>

## Notes

- See the [raw source code](https://raw.githubusercontent.com/MUSA-550-Fall-2021/github-pages-starter/main/_posts/2021-11-29-measles-charts.md) of this post for details on how these charts were embedded.
- See the [lecture 13A slides](https://github.com/MUSA-550-Fall-2021/week-13/blob/main/lecture-13A.ipynb) for the code that produced these plots.

**Important: When embedding charts, you will likely need to adjust the width/height of the charts before embedding them in the page so they fit nicely when embedded.**
