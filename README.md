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

Data cleaning and data exploration 

**Variables:**

The dataset contains 13 columns which are:

stn_code: Station code 

sampling_date: Date of sampling (formated by month, day, year)

state: State 

location: Location of recording 

agency: Agency 

type: Type of area 

so2: Sulphur dioxide (ug/m3)

no2:

rspm: 

spm:

location_monitoring_station:

pm2_5:

date:

I also added a column that has only the year from the date column
**References:**




