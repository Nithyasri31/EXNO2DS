# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
dt=pd.read_csv("/content/titanic_dataset (2).csv")
dt
```
![image](https://github.com/user-attachments/assets/afd2a80e-102b-4789-9542-6d957737abd7)
```
dt.info()
```
![image](https://github.com/user-attachments/assets/0536dca5-36c2-42b0-a61b-2841a8e0dfe5)
```
dt.shape
```
![image](https://github.com/user-attachments/assets/da6c230e-dfe2-4356-91a0-7ca09d2fc372)
```
dt.set_index("PassengerId",inplace=True)
dt.nunique()
```
![image](https://github.com/user-attachments/assets/0b0ddb83-152d-4300-a509-fd6073d2453f)
```
dt["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/17b3e630-96c9-460b-8e49-53eb52478cfe)
```
per=(dt["Survived"].value_counts())
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/f78fe817-b1d1-44cd-ae18-70f39cf487bd)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/user-attachments/assets/9eb0b173-7fa2-4a79-8558-44f005c8764c)
```
dt
```
![image](https://github.com/user-attachments/assets/7ab20e56-0f9e-4398-bfcd-0c2a9d5ec1e9)
```
dt.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/ff764bf1-338c-4c8d-921a-b60125317a74)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/user-attachments/assets/a85ea08f-7de8-456d-a990-2a5db7e97bd9)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/b98a386d-4d23-42e7-887b-44ae0f654556)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/user-attachments/assets/38769e42-4c5b-4ed8-abef-7ccc4d6e5e40)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/5ffb019d-cf0f-42d2-894f-04782092930f)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/user-attachments/assets/d23fe5ba-b0b4-440d-bca1-211a0ddcc15a)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/user-attachments/assets/d4b1531f-9a66-4b14-ac9f-0f7c6e343fec)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/user-attachments/assets/1768518c-1e1e-47e4-b29a-88affadce64c)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/020ed9ab-3b95-4ee0-9af3-e7eced0e2af9)
```
numeric_dt=dt.select_dtypes(include=['int64','float64'])
corr=numeric_dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/73f9135e-0dec-412a-b56c-9307607e2111)
```
sns.pairplot(dt)
```
![image](https://github.com/user-attachments/assets/f3932c81-1f90-4166-a5fc-c8da625eba43)

# RESULT
Exploratory Data Analysis is successfully performed on the given data set.

