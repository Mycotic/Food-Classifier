# Food-Classifier
Numen Rubino

Sources: US Department of Agriculture
https://fdc.nal.usda.gov/download-datasets.html

## Introduction
The goal of this classifier is to identify foods containing meat based on the food's nutrients. This could be useful for market analysis or as a tool for vegetarians or people with allergies to find out if a food is likely to contain meat. I used recall as my classifier to minimize the how often the model mislabels meat specifically. My final model had a recall of 98%, which might be good enough for vegetarians but probably not for people with meat allergies.

## Labeling Process
The data originally had labels describing the general category the food was in, like pasta, protein shakes, beef, etc. I selected categories that should mostly be vegetarian or mostly contain meat and labeled samples in those categories as meat or not meat. Uncertain food categories were not used in the modeling process, like "sweets" (because of gelatin), "soups, broths, and sauces," and others.
