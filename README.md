# ODD2023-Datascience-Ex-04
# AIM:
### To perform Multivariate EDA on the given data set.

# EXPLAINATION:
#### Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
## Step1: 
#### Import the built libraries required to perform EDA and outlier removal.
## Step2:
#### Read the given csv file.
## Step3:
#### Convert the file into a dataframe and get information of the data.
## Step4: 
#### Return the objects containing counts of unique values using (value_counts()).
## Step5: 
#### Plot the counts in the form of Histogram or Bar Graph.
## STEP 6
#### Use seaborn the bar graph comparison of data can be viewed.
## STEP 7
#### Find the pairwise correlation of all columns in the dataframe.corr()
## STEP 8
#### Save the final data set into the file.
# PROGRAM:
```
Developed By: SRINIDHI SENTHIL
Register Number:212222230148

import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('SuperStore.csv')
df.describe()
df.isnull().sum()
df.info()
# FILLING NULL VALUES
df['Postal Code']=df['Postal Code'].fillna(df['Postal Code'].mode()[0])
sns.boxplot(df)
sns.scatterplot(x=df['Region'],y=df['Sales'])
plt.figure(figsize=(10,3))
sns.barplot(x=df['State'],y=df['Sales'])
plt.xticks(rotation=90)
sns.heatmap(df.corr(),annot=True)
sns.displot(df,x='Region',hue="Category")
```
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/c5042567-00d5-4c23-8abb-a2029b56ae63)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/9e8f4939-b468-4302-9073-11276501879c)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/f98f118e-3035-4d4e-b345-77d7e6278e6f)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/7ded794e-a9b1-4c94-806a-816207254263)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/cced6367-35a0-4492-9488-a2658cef1665)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/13e1ef68-f212-453f-870d-e260194a608b)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/4b053fb9-9eab-400b-a497-14288e67087c)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/9682a83c-ab75-4649-9659-cdfacee4ec47)
```
import pandas as pd
import seaborn as sns
from scipy import stats
import matplotlib.pyplot as plt
df=pd.read_csv('diabetes.csv')
df.describe()
df.isnull().sum()
# REMOVING OUTLIER
z = np.abs(stats.zscore(df['Glucose']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
df=df[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
df=df[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
df=df[(z<3)]
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.boxplot(data=dfc)
plt.xticks(rotation=90)
sns.scatterplot(x=df['Glucose'], y=df['BloodPressure'], hue=df['Outcome'])
Age=df.loc[:,["Age","BMI"]]
Age=Age.groupby(by=["Age"]).sum().sort_values(by="BMI")
plt.figure(figsize=(12,5))
plt.xticks(rotation=90)
sns.barplot(x=Age.index,y="BMI",data=Age)
sns.boxplot(x=df['DiabetesPedigreeFunction'],y=df['Insulin'])
sns.displot(df, x="Glucose", hue="Outcome")
df.corr()
sns.heatmap(df.corr(),annot=True)
```
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/7fbf2251-1aef-4cd6-8866-5e38f4c085d6)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/16e01081-ec44-42a5-9185-2ff3ceca9c8a)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/52a1a988-25bd-4d95-8956-33f6f68ca479)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/633ac96f-3287-4b2b-a673-e2560bda7805)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/5c7fba5b-aea5-42d2-8c2e-1c1aecd5abb4)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/63692e8a-0d95-44b0-a4f8-c1ec659a9359)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/7340a7be-50c3-4004-a02b-07e34008169a)
![image](https://github.com/SRINIDHISENTHILNATHAN/ODD2023-Datascience-Ex-04/assets/121373170/060691aa-48fc-4ed9-af8e-3018b07e34e0)
# RESULT:
Thus we have read the given data and performed the multivariate analysis with different types of plots.
