---
title: "Spatial Analysis of Positive and Negative tweets"
date: 2021-12-19
published: true
tags: [dataviz, pysal,geopandas,hvplot]
excerpt: "Where postive and negative tweets come from"
hv-loader:
  hv-chart-1: ["charts/pos_moran.html"] 
  hv-chart-2: ["charts/neg_moran.html"] 
toc: true
toc_sticky: true
---

Introduce global/spatial Moran's I and Pysal package.(Hasa)

## Build spatial weight matrix

see reference [here](http://jurgens.people.si.umich.edu/tutorials/Mapping_Word_Frequencies_on_Twitter_using_Python.html): (Hasa)

```python
us_centroid = merged_emo[['geometry']].copy()
us_centroid.geometry = merged_emo.centroid
fig, ax = plt.subplots(1, figsize=(11,8.5))
ax.axis('off')
us_centroid.plot(ax=ax, marker='*', color='red', markersize=1)
merged_emo.plot(ax=ax, facecolor="none", linewidth=0.4, edgecolor='0')
```    
![swm]({{ site.url }}{{ site.baseurl }}/assets/images/swm.png)

```python
swm5 = KNN.from_dataframe(merged_emo, k=5)
```

## the Global Moran's I

```python
pos_mi = Moran(merged_emo.positive, swm5)
print("Global Moran's I for positive tweets:", pos_mi.I) 
print("Global Moran's p-value: %0.19f" % pos_mi.p_norm)
```
>Global Moran's I for positive tweets: 0.20532576507819358  
>Global Moran's p-value: 0.0050474715951336346

```python
neg_mi = Moran(merged_emo.negative, swm5)
print("Global Moran's I for negative tweets:", neg_mi.I) 
print("Global Moran's p-value: %0.19f" % neg_mi.p_norm) 
```
>Global Moran's I for negative tweets: 0.1751399589405492
>Global Moran's p-value: 0.0150793448129815655

## Local Moran's I

```python
gol = pysal.explore.esda.G_Local(merged_emo['positive'], swm5, transform='B')
merged_emo['positive_I'] = gol.Zs
cols = ["positive_I", "State_Name", "positive", "geometry"]
pos_moran=merged_emo.hvplot(c="positive_I", 
                    width=600,
                  height=350,
                    cmap='cet_CET_D9',
                    hover_cols=["positive","State_Name"])
```
<div id="hv-chart-1"></div>
<div id="hv-chart-2"></div>

- See the [spatial analysis](https://github.com/Anran0716/550final-proj/blob/main/code/spatial%20analysis.ipynb) for the code that produced these plots.
