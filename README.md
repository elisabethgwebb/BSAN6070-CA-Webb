**BSAN6070-CA-Webb: CA01 - Data Cleaning and Exploration of India Air Quality**

Elisabeth Webb - BSAN6070 Assignments

**Instructions for the reader:**

**Packages to import:**

import pandas as pd 

import numpy as np 

from sklearn.impute import SimpleImputer

import matplotlib as mpl

import matplotlib.pyplot as plt

plt.style.use('seaborn-colorblind')

**Data Source:**
The data came from a kaggle dataset named [India Air Quailty](https://www.kaggle.com/shrutibhargava94/india-air-quality-data).

read datasets

data=pd.read_csv('data.csv')

**Techniques:**

Focused on data cleaning and data exploration. 

data.describe() for a statistical description 

data.shape for the number of rows and columns 

data.count() for the number of non-nill values for each column and data.isnull().sum() for the number of null values in each column. 

data.info() for the range, column names, non-null items in each column, datatype, and memory usage.  

data.head(10) and data.tail(10) for the top and bottom 10 rows of the dataset. 

**Variables:**

The dataset contains 13 columns which are:

stn_code: Station code 

sampling_date: Date of sampling (formated by month, day, year)

state: State 

location: Location of recording 

agency: Agency 

type: Type of area 

so2: Sulphur dioxide (ug/m3)

no2: Nitrogen dioxide (ug/m3)

rspm: Respirable Suspended Particle Matter (ug/m3)

spm: Suspended PArticle Matter (ug/m3)

location_monitoring_station: Location of data collection 

pm2_5: PSI 2.5(ug/m3)

date: date of sampling 

I also added a column that has only the year from the date column

**References:**

https://stackoverflow.com/questions/39436018/how-to-drop-null-values-in-pandas

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.drop.html

https://www.interviewqs.com/ddi_code_snippets/extract_month_year_pandas

https://scikit-learn.org/stable/modules/generated/sklearn.impute.SimpleImputer.html

https://scikit-learn.org/stable/modules/impute.html

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.dropna.html#pandas.DataFrame.dropna

https://stackoverflow.com/questions/5159065/need-to-add-space-between-subplots-for-x-axis-label-maybe-remove-labelling-of-a

https://matplotlib.org/3.1.0/api/_as_gen/matplotlib.pyplot.subplots_adjust.html





