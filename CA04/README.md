# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments
CA04 Ensemble Models

## Data: ##
The data can be accessed and read in using this link https://raw.githubusercontent.com/ArinB/MSBA-CA-03-Decision-Trees/master/census_data.csv

It is also located in the CA04 folder called "census_data.csv". 

## Libraries to Import: ##

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

from sklearn import tree

from sklearn.tree import DecisionTreeClassifier

from sklearn.model_selection import train_test_split

from sklearn.ensemble import RandomForestClassifier

from sklearn.ensemble import AdaBoostClassifier

from sklearn.ensemble import GradientBoostingClassifier 

import xgboost as xgb 

from xgboost import XGBClassifier

from sklearn.metrics import roc_auc_score

## Instructions to Run: ##

If you system hasn't installed scikit-learn or xgboost, you will need to uncomment the codes #pip install -U scikit-learn and #pip install xgboost in the CA04_ElisabethWebb.ipbyn notebook and and run them each once. Run each section in the file named CA04_Elisabeth_Webb.ipynb in the CA04 folder. Each section in the notebook is labelled above the code and explained either in detailed comments or a text section below the code. 

## Method: ##

First we import the necessary libraries, read in the data, and clean it. After preprocessing the data, we split it into train and test sets. We then take the categorical variables and convert them into dummies, because the classification models don't support categorical columns. After getting the data into the necessary format for the models, we find the optimal max_depth for the DecisionTreeClassifer by testing values between 2 to 20 and plotting the results. Next, we build a RandomForestClassifer model and test different n_estimators between 50 to 500. By plotting a graph of the results, we can identify which produces the highest accuracy. We repeat the same process with the AdaBoost, Gradient Boost, and XGB models. Lastly, we use the common hyper-parameters of n_estimators=150 and random_state=101 in each of these models and compare their performance in terms of accuracy and auc in a table. The value of 150 estimators was used in each model, because that is the number of estimators in which the random forest model in the beginning performed the best, so the goal is to compare how other models perform using the same hyper-parameter value. 


## Summary: ##
From this assignment, I have learned how to create ensemble models such as Random Forest, AdaBoost, Gradient Boost, and XGB in python as well as understanding how bagging and boosting methods work from the class lecture. The results from this analysis show how the number of estimators affects each model's performance. When using the same common hyper-parameter of 150 estimators in each model, the XGB model has the highest accuracy and auc values. When choosing an ensemble model for this dataset to use for prediction I would use the XBG model, because it performs the best under these common hyper-parameters.

