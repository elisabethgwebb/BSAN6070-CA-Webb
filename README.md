# BSAN6070-CA-Webb
Elisabeth Webb - BSAN6070 Assignments
# import packages 
import pandas as pd 
import numpy as np 
from sklearn.impute import SimpleImputer
import matplotlib as mpl
import matplotlib.pyplot as plt
plt.style.use('seaborn-colorblind')

#read datasets
data=pd.read_csv('data.csv')
data.head(10)

# Your code for this section here ...
#descriptive statistics
data.describe() #1
data.shape #2
data.count() #3
data.isnull().sum() #4
data.info() #5
data.head(10) #6
data.tail(10) #6

# Cleaning up the data

#dropping columns that aren't required

# ... your code here
data=data.drop(columns=['stn_code','agency','sampling_date','location_monitoring_station'], axis=1)

# dropping rows where no date is available

# ... your code here
data.dropna(subset=['date'], how='all', inplace=True)
data['date'].isnull().sum()
# displaying final columns (data.columns)

# ... your code here
data.columns

# ... Your code here
types = { "Residential": "R", "Residential and others": "RO", "Residential, Rural and other Areas": "RRO", "Industrial Area": "I", "Industrial Areas": "I", "Industrial": "I", "Sensitive Area": "S", "Sensitive Areas": "S", "Sensitive": "S", np.nan: "RRO" }
data.type=data.type.replace(types)

# Display top 10 records after codification of 'types'
# ... Your code here
data.head(10)

# ... Your code here
import datetime
data = pd.DataFrame(data)
data['year']=pd.to_datetime(data['date'])
data['year'] = pd.DatetimeIndex(data['date']).year
data.head(5)
data.info()

# define columns of importance, which shall be used reguarly (COLS = ....)
# invoke SimpleImputer to fill missing values using 'mean' as the replacement strategy
# Display data.info after the transformation
# Display that there are no more missing values in the dataset

# ... your code here
COLS = ['so2','no2','rspm','spm','pm2_5']
imp = SimpleImputer(missing_values=np.nan, strategy='mean')
imp.fit(data[COLS])
data[COLS]=pd.DataFrame(imp.transform(data[COLS]), index=data.index)
data.info() #after the transformation
data.isnull().sum() #no more missing values in the dataset 

# ... Your code here
state_so2=data.groupby('state')['so2'].median().sort_values()
#barchart  
plt.bar(state_so2.index, state_so2, color='red')
plt.ylabel('SO2 Status')
plt.xlabel('State')
plt.ylim(None,30)
plt.xticks(rotation=90)
plt.show()

# ... Your code here
state_no2=data.groupby('state')['no2'].median().sort_values()
#barchart  
plt.bar(state_no2.index, state_no2, color='blue')
plt.ylabel('NO2 Status')
plt.xlabel('State')
plt.ylim(None,60)
plt.xticks(rotation=90)
plt.show()

# ... Your code here
state_rspm=data.groupby('state')['rspm'].median().sort_values()
#barchart  
plt.bar(state_rspm.index, state_rspm, color='purple')
plt.ylabel('RSPM Status')
plt.xlabel('State')
plt.ylim(30,170)
plt.xticks(rotation=90)
plt.show()

# ... Your code here
state_spm=data.groupby('state')['spm'].median().sort_values()
#barchart  
plt.bar(state_spm.index, state_spm, color='green')
plt.ylabel('SPM Status')
plt.xlabel('State')
plt.ylim(70,275)
plt.xticks(rotation=90)
plt.show()

# ... Your code here
data_new=data[data['state']=='Andhra Pradesh'].groupby('year')[['no2','so2','rspm','spm']].mean()
data_new.head(5)

# Display yearly trend graph (year vs. value) in pairs: (a) so2 and no2 (b) rspm and spm. 
# So, you will display TWO graphs altogether.

# ... Your code here
plt.subplot(2,1,1)
plt.plot(data_new.groupby('year')['so2'].mean(),c='red',linestyle='-',label='SO2 Yearly Level')
plt.plot(data_new.groupby('year')['no2'].mean(), c='blue',linestyle='-', label='NO2 Yearly Level')
plt.legend()
plt.title('SO2 and NO2 Yearly Trend')

plt.subplot(2,1,2)
plt.plot(data_new.groupby('year')['rspm'].mean(),c='purple',linestyle='-',label='RSPM Yearly Level')
plt.plot(data_new.groupby('year')['spm'].mean(), c='green',linestyle='-', label='SPM Yearly Level')
plt.legend()
plt.title('RSPM and SPM Yearly Trend')
plt.subplots_adjust(hspace=.5)

This analysis shows that from 1990 to 2015 in the state of Andhra Pradesh, nitrogen dioxide (no2) and sulfur dioxide both follow a similar trend of varying levels. However, no2 spikes around 2012, while so2 decreases then. No2 is higher in 2015 than 1990, while so2 is lower in 2015 than 1990. The second graph provides a couple interesting points. It shows that SPM drops in the early 2000s, and then quickly and drastically rises again from 100 ug/m3 to over 200 ug/m3. Around that same time period, RSPM levels begin to drop from its 12 year plateau of 120 ug/m3. SMP levels rise again and are higher in 2015 than 1990, while RSPM levels are lower in 2015 than 1990. This tells us that we should look into the year 2002 for why RSPM began to drop from previously staying the same level, and why RSPM dropped to its lowest level and then quickly rose again. In the state of Andhra Pradesh from 1990 to 2015, we can conclude that no2 and so2 levels follow similar trends of fluctuating levels, while RSPM drops and SPM wavers but overall increases. This information is helpful for us to further look into the reasons why drops or increases in levels happened in certain years as well as seeing the overall trend during this time period.
