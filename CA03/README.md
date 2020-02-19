# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments
CA03 Decision Tree Algorithm 

##Data##
The data can be accessed and read in using this link https://raw.githubusercontent.com/ArinB/MSBA-CA-03-Decision-Trees/master/census_data.csv

It is also located in the CA03 folder. 

##Libraries to Import:##
If you have not already, you will need to !pip install scikit-plot once. The following are the libraries used that need to be imported for running the program. 

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

import scikitplot as skplt

from sklearn.metrics import classification_report

##Instructions to Run:##

Run each section in the file named CA03_Elisabeth_Webb.ipynb in the CA03 folder.

##Method:##

First we read in the data, clean it, and do exploratory data analysis through creating stacked bar charts. After preparing the data and visualizing it, we begin building the decision tree classification model. 
##Summary:##
