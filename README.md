# Food-Classifier
Numen Rubino

Sources: US Department of Agriculture
https://fdc.nal.usda.gov/download-datasets.html

## Introduction
The goal of this classifier is to identify foods containing meat based on the food's nutrients. This could be useful for market analysis or as a tool for vegetarians or people with allergies to find out if a food is likely to contain meat. I used recall as my classifier to minimize the how often the model mislabels meat specifically. My final model had a recall of 98%, which might be good enough for vegetarians but probably not for people with meat allergies.

## Labeling Process
The data originally had labels describing the general category the food was in, like pasta, protein shakes, beef, etc. I selected categories that should mostly be vegetarian or mostly contain meat and labeled samples in those categories as meat or not meat. Uncertain food categories were not used in the modeling process, like "sweets" (because of gelatin), "soups, broths, and sauces," and others.

## Data Preprocessing
Samples that had more than 100g of a nutrient per 100g were removed. The kilojoules feature was also removed because it had high correlation with kilocalories in the samples that did have kJ measurements. One of each feature pair with at least a .8 correlation was removed until no features had a .8 correlation with another one. Vegetarian samples were also downsampled before modeling to resolve class imbalance.

## Modeling
Random forest and xgboost models were tried - the random forest performed better and performed quite well so xgboost wasn't optimized. Random forest had a recall of .988 and an accuracy of .99, whereas the xgboost had a recall of .96.


## False Negative and False Positive Classes
![](https://raw.githubusercontent.com/Mycotic/Food-Classifier/main/figs/fpos_eg.png)

![](https://raw.githubusercontent.com/Mycotic/Food-Classifier/main/figs/fneg_eg.png)

![](https://raw.githubusercontent.com/Mycotic/Food-Classifier/main/figs/__fneg_percent.png)

![](https://raw.githubusercontent.com/Mycotic/Food-Classifier/main/figs/__fpos_percent.png)

Download:
https://fdc.nal.usda.gov/fdc-datasets/FoodData_Central_csv_2020-04-29.zip