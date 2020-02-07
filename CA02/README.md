# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments

## Data: ##

The datasets (train and test) are zipped together in folder named Data that is in the CA02 folder. 

## Libraries to Import: ##

import os

import numpy as np

from collections import Counter

from sklearn.naive_bayes import GaussianNB

from sklearn.metrics import accuracy_score

## Instructions to Run: ##

Run each section in the file named CA02_Elisabeth_Webb.ipynb in the CA02 folder. 

## Method: ##
The first step is to clean and prepare the data by removing expressions, symbols, and stop words. Next, create a dictionary with the 3000 most common words from all the emails. To do this, a function needs to be created that will remove those items and leave only alphabetic words for the analysis. Then, create a feature matrix that will store each word as a column and each email as a row. The next step is to create another function that will look at how each file is named and determine if it is spam or not spam and store it as a labelled data column. The feature is used on both the training and testing dataset and will return a labelled data columns and a feature matrix for each. After creating the two functions, the program executes them. It fits the Gaussian model to the training dataset, and then it runs the now trained model with the test data and uses that to score the model's preformance in terms of accuracy of predicting the email's category (spam or not spam). 

## Summary: ##
