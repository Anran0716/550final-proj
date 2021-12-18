---
title: "Machine learning "
date: 2019-12-08T15:34:30-04:00
published: true
tags: [marching learning, model validation,skilearn]
excerpt: "Find out the best model to Predict the postive tweets"
toc: true
toc_sticky: true
---

In this part, we decided to build a machine learning model to help the new Airbnb hosts set their price. (Hasa)

A picture showing the workflow of ML.  

## Data Processing
The first step of data processing is handling outliers. 
We examined the price distribution, filtered the outliers, as well as removed the  NA value of potential features. The final dataset contains 26624 observations.     
  
```python
tweets_df['senti_label']=tweets_df.Sentiment.apply(lambda x: 0 if 'Negative'in x else 1 if 'Netural' else 5)
y=tweets_df['senti_label']
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer(max_features=3000)
X_fin=cv.fit_transform(cleaned_data).toarray()
X_train,X_test,y_train,y_test=train_test_split(X_fin,y,test_size=0.3, random_state=123)
```    

## Compare with different models
We selected several potential variables that might influence the price of Airbnband, and loaded the data from NY opendata and OSM, including the crime data, 311 requests data, university, subway and attractions. (Hasa)

**Random forest**  

```python
from sklearn.ensemble import RandomForestClassifier
rf_clf = RandomForestClassifier(n_estimators=250, random_state=0) 
rf_clf.fit(X_train, y_train) 
y_pred1 = rf_clf.predict(X_test)

print("Results for Random forest")
print("Accuracy:",accuracy_score(y_test,y_pred1))
```    
> Results for Random forest  
Accuracy: 0.9303172126885075  

**Logistic Regression**  
```python
from sklearn.linear_model import LogisticRegression
log_model = LogisticRegression()
log_model = log_model.fit(X=X_train, y=y_train)
y_pred2 = log_model.predict(X_test)
```

> Results for Logistic Regression  
Accuracy: 0.921996879875195 

**Support Vector Machine**
  
```python
svcl = svm.SVC()
svcl.fit(ctmTr, y_train)
svcl_score = svcl.score(X_test_dtm, y_test)
y_pred3 = svcl.predict(X_test_dtm)
```
> Results for Support Vector Machine     
 Accuracy: 0.9022360894435777
 
**K Nearest Neighbor**
```python
from sklearn.neighbors import KNeighborsClassifier
knn = KNeighborsClassifier(n_neighbors=5)
knn.fit(ctmTr, y_train)
knn_score = knn.score(X_test_dtm, y_test)
y_pred4 = knn.predict(X_test_dtm)
```
> Results for K Nearest Neighbor    
 Accuracy: 0.8959958398335933
 
 picture for confusion matrix.  
 
![CM]({{ site.url }}{{ site.baseurl }}/assets/images/CM.PNG)

## Validation  
For the test set, we calculated the predicted price, percent error as well as absolute percent error for each observation.
```python
rf_clf.fit(x1,y1)
test_sentence = vectorizer.transform(['I love covidvaccine!'])
rf_clf.predict_proba(test_sentence)
```

> array([[0.13118602, 0.86881398]])   

To further examine the spatial autocorrelation, we visualized the spatial distribution of the percent error , as well as the mean absolute percet error by neighborhood in test set. It is clearly that the errors of prediction Airbnb price have few spatial cluster (i.e.The ones with high error are clustered together, and so do the ones with low error), which means the effects of spatial autocorrelation have reduced a lot.
     
Overall, though remaining a few flaws in our model, we still believe that this model will perform well in Airbnb which enjoys a wider range of data collection channels.This new pricing guide feature could be attached in User Interface, and hosts that subscribe this feature could be charged in reasonable price. (Hasa)

- See the code of [Machine Learning](https://github.com/Anran0716/550final-proj/blob/main/code/ML.ipynb).
