# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments
CA03 Decision Tree Algorithm 

## Data: ##
The data can be accessed and read in using this link https://raw.githubusercontent.com/ArinB/MSBA-CA-03-Decision-Trees/master/census_data.csv

It is also located in the CA03 folder. 

## Libraries to Import: ##

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

from sklearn import tree

from sklearn.tree import DecisionTreeClassifier

from sklearn.model_selection import train_test_split

from sklearn.externals.six import StringIO  

from sklearn.tree.export import export_text

from IPython.display import Image  

from sklearn.tree import export_graphviz

import pydotplus

import graphviz 

from sklearn import metrics

from sklearn.metrics import confusion_matrix

from sklearn.metrics import precision_recall_curve

from sklearn.metrics import plot_precision_recall_curve

import matplotlib.pyplot as plt

from sklearn.metrics import precision_score

from sklearn.metrics import recall_score

from sklearn.metrics import f1_score

from sklearn.metrics import roc_auc_score

from sklearn.metrics import classification_report

from sklearn.metrics import plot_roc_curve

## Instructions to Run: ##

You will need to upload the automation_hypar.csv and the new_individual.csv files before running the program. You will also need to !pip install ipython.autotime %load_ext autotime in order to see the time it takes to run each cell. Run each section in the file named CA03_Elisabeth_Webb.ipynb in the CA03 folder. Each section in the notebook is labelled, and there is detailed comments explaining the code. 

## Method: ##

First we read in the data, clean it, and do exploratory data analysis through creating stacked bar charts. After preparing the data and visualizing it, we begin building the decision tree classification model. This is done through a library in sklearn called DecisionTreeClassifier. Before using the algorithm we need to split the data into train and test and create dummy variables for the categorical variables, because the classifier doesn't work with categorical variables. For the first tree, I didn't specify any hyperparemeters other than random_state=100 to ensure that the program runs multiple times. For the other hyperparemeters, I used the default settings. Next, we visualize the decision tree and evaluate its preformance using a confusion matrix, accuracy, precision, recall, F1 Score, AUC Value, and ROC Curve Graph. Then we will alter the hyperparameters of Split Criteria, Minimum Sample Split, Minimum Sample Leaf, and Maximum Depth both manually and automatically to find a tree that produces the highest metrics. Lastly, we will use the trained model to predict a new individual's unknown income category and evaluate the accuracy based on the probability that the predicition is in each category. 

## Summary: ##

The goal of this assignment was to use decision trees to predict the income level of individuals. We evaluated the trees using confusion matrix, accuracy score, precision, recall, and the F1 score. After training the model, we used it to predict an unknown income level. It predicted that the income level for that person was >50K. The probability of that prediction being correct was 93%. 
