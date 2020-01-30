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

dropped columns that I didn't use for analysis: 

data=data.drop(columns=['stn_code','agency','sampling_date','location_monitoring_station'], axis=1)

Dropped rows where no date was available: 

data.dropna(subset=['date'], how='all', inplace=True)

changed the format of the type column (type of area) by creating a dictionary: 

types = { "Residential": "R", "Residential and others": "RO", "Residential, Rural and other Areas": "RRO", "Industrial Area": "I", "Industrial Areas": "I", "Industrial": "I", "Sensitive Area": "S", "Sensitive Areas": "S", "Sensitive": "S", np.nan: "RRO" }

data.type=data.type.replace(types)

Used datatime package to take only the year out of the date and put it in a new column. 

data = pd.DataFrame(data)

data['year']=pd.to_datetime(data['date'])

data['year'] = pd.DatetimeIndex(data['date']).year

Used SimpleImputer from sklearn-imputer to replace some columns with the mean:

COLS = ['so2','no2','rspm','spm','pm2_5']

imp = SimpleImputer(missing_values=np.nan, strategy='mean')

imp.fit(data[COLS])

data[COLS]=pd.DataFrame(imp.transform(data[COLS]), index=data.index)

data.info() #after the transformation

data.isnull().sum() #no more missing values in the dataset 

Next grouped by state and so2, no2, rspm, or spm to show the median value by ascending order and displayed in a bar graph. 

state_so2=data.groupby('state')['so2'].median().sort_values()

plt.bar(state_so2.index, state_so2, color='red')

Lastly, only where the state was Andhra Pradesh grouped by year to show no2, so2, rsp, and spm. Then displayed two line graphs. One to show the trend of no2 and so2 and the other rspm and spm together from 1990 to 2015. 

data_new=data[data['state']=='Andhra Pradesh'].groupby('year')[['no2','so2','rspm','spm']].mean()

plt.plot(data_new.groupby('year')['so2'].mean(),c='red',marker='o', markersize=3, linestyle='-',label='SO2 Yearly Level')

plt.plot(data_new.groupby('year')['no2'].mean(), c='blue', marker='o', markersize=3,linestyle='-', label='NO2 Yearly Level')

plt.plot(data_new.groupby('year')['rspm'].mean(),c='purple',marker='o', markersize=3, linestyle='-',label='RSPM Yearly Level')

plt.plot(data_new.groupby('year')['spm'].mean(), c='green',marker='o',markersize=3, linestyle='-', label='SPM Yearly Level')

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





