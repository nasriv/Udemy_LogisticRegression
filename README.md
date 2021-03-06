# Logistic Regression Project
*Based on Udemy class "Python for Data Science and Machine Learning Bootcamp" by Jose Portilla*

## Logistic Regression Project ##
In this project we will be working with a fake advertising data set, indicating whether or not a particular internet user clicked on an Advertisement. 

__We will try to create a model that will predict whether or not they will click on an ad based off the features of that user__

This data set contains the following features:
Column Name | Description
-------------|------------
'Daily Time Spent on Site'| consumer time on site in minutes
'Age'| cutomer age in years
'Area Income'| Avg. Income of geographical area of consumer
'Daily Internet Usage'| Avg. minutes a day consumer is on the internet
'Ad Topic Line'| Headline of the advertisement
'City'| City of consumer
'Male'| Whether or not consumer was male
'Country'| Country of consumer
'Timestamp'| Time at which consumer clicked on Ad or closed window
'Clicked on Ad'| 0 or 1 indicated clicking on Ad

## Exploratory Data Analysis ## 

<img src="https://github.com/nasriv/Udemy_LogisiticRegression/blob/master/AgeHist.jpg" width="350"> <img src="https://github.com/nasriv/Udemy_LogisiticRegression/blob/master/Joint_AgeAreaIncome.jpg" width="450"> 

<img src="https://github.com/nasriv/Udemy_LogisiticRegression/blob/master/heatmap.jpg" width="700">

<img src="https://github.com/nasriv/Udemy_LogisiticRegression/blob/master/pairplot.jpg" width="700">

## Logisitic Regression Model ## 
``` python
# ---- define X and y databases to drive logistic model
X = ads.drop(['Ad Topic Line','City','Country','Timestamp','Clicked on Ad'],axis=1)
y = ads['Clicked on Ad']

# ---- design test and training set
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=101)
logm = LogisticRegression().fit(X_train,y_train)

```
## Predictions and Evaluation ##
``` python 
# -- predict results based on log model
predictions = logm.predict(X_test)

# --- output confusion matrix and classification matrix
print(confusion_matrix(y_test,predictions))
print(classification_report(y_test,predictions))
```
