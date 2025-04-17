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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/0e96b31c-37a2-49e0-8147-904075d01ee5)
```
df.info()
```
![image](https://github.com/user-attachments/assets/1d286b3b-c7b4-4a1a-b202-eea6f616fee5)
```
df.shape
```
![image](https://github.com/user-attachments/assets/bc659f03-1b00-422e-b21c-e0193e069843)
```
df.set_index('PassengerId',inplace=True)
df.nunique()
```
![image](https://github.com/user-attachments/assets/f40490b8-03b7-4b86-b340-e61e9da1afed)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/45ea82dc-52b3-4a80-98a1-71a1fb9d729d)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/59d8113c-3b50-4529-ae37-0f9291ebb222)
```
sns.countplot(data=df,x="Survived")
```
![download (6)](https://github.com/user-attachments/assets/462d1f3b-70ce-48ce-a156-01e56a180669)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/f11107db-30ef-40b0-8918-29c22b7f511f)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/5d4c0ff4-6066-499b-b236-ce6918790417)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![download (7)](https://github.com/user-attachments/assets/1329363a-a1cc-4efe-a2f6-4e85d200c32a)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![download (8)](https://github.com/user-attachments/assets/eac55dca-e262-40d5-964a-eee1afc7fd5f)
```
df.boxplot(column="Age",by="Survived")
```
![download (9)](https://github.com/user-attachments/assets/bd167857-f9af-47cc-93e5-d03198cf637f)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![download (10)](https://github.com/user-attachments/assets/d34bc440-df63-4920-a722-61a4b37b3798)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![download (11)](https://github.com/user-attachments/assets/3e72a4b5-2acc-4676-9713-1035083a5d5a)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt= sns.boxplot(ax=ax1,x="Pclass",y='Age',hue="Gender",data=df) 
```
![download (12)](https://github.com/user-attachments/assets/beac053d-e0e6-43b0-82c2-977b78c0afdb)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![download (13)](https://github.com/user-attachments/assets/8d987587-015d-47bb-899c-3ad2bb7dea21)
```
numerical_features = df.select_dtypes(include=np.number).columns
corr = df[numerical_features].corr()
sns.heatmap(corr, annot=True)
```
![download (14)](https://github.com/user-attachments/assets/3e93da8c-27b6-4558-8229-b4d43e597b55)
```
sns.pairplot(df)
```
![download (15)](https://github.com/user-attachments/assets/e3ca76dd-723b-4121-b535-704079f19f4b)

# RESULT
        <<INCLUDE YOUR RESULT HERE>>
