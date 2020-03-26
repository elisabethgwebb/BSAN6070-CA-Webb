# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments
CA05A - Logistic Regression

## Data: ##
The data can be accessed and read in using this link https://raw.githubusercontent.com/ArinB/CA05-B-Logistic-Regression/master/cvd_data.csv

## Libraries to Import: ##

import pandas as pd

from sklearn.model_selection import train_test_split

import numpy as np

from sklearn import preprocessing

from sklearn.linear_model import LogisticRegression 

from sklearn.metrics import accuracy_score 

import seaborn as sns 

import matplotlib.pyplot as plt

import sklearn.linear_model as lm

from sklearn.metrics import classification_report

from sklearn.metrics import roc_auc_score

from sklearn.metrics import plot_roc_curve

from sklearn.metrics import precision_score

from sklearn.metrics import recall_score

from sklearn.metrics import f1_score

from sklearn import metrics

## Instructions to Run: ##

Run each section in the file named ElisabethWebb_CA05_A.ipynb in the CA05A folder. Each section in the notebook is labelled above the code and explained either in detailed comments below the code. 

## Method: ##

First we import the necessary libraries, read in the data, and check for multicollinearity using a correlation matrix. After removing the variables that have a correlation above 0.7 (hip), then I converted the categorical variables into dummies. Next, I identified the X and y, and then split it into train and test sets. After getting the data into the necessary format, I built the logistic regression model, fit it to the training dataset, and then evaluated it's performance on the test dataset. 


## Findings: ##
The results from this analysis show the most important features in the dataset which are waist followed by health limiting social activites level 4/5 and marital status 1 (being married). When using the model for prediction, I found that the model predicted the risk of cardiovascular disease on the test dataset with about 69% accuracy. When evaluating the model’s performance using accuracy score, precision, recall, f1 score, AUC value, and the ROC graph, the results show that precision and recall are balanced because the f1 score is high. Accuracy is also relatively high at 69%. The AUC value from the predicted scores is 0.64, which is not particularly high as 0.5 means the classification is almost random 50-50. When plotting the ROC from X_test and y_test, it shows that the AUC is 0.71. These scores indicate that the model is acceptable and does a better job than random, but it is not an excellent model in its ability to classify patient’s CVD risk based on these independent variables.
