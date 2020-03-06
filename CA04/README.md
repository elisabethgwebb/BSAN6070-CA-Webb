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

First we import then necessary libraries, read in the data, and clean it. After pre-processing the data, we split it into train and test sets. We then take the categorical variables and convert them into dummies, because the classification models don't support categorical columns. After getting the data into the necessary format for the models, we....


## Summary: ##

