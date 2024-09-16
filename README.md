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
## DEVELOPED BY : RADHIMEENA M
## REG NO :212223040159 
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
```
df.head(10)
```
```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/09253742-13a9-4514-aa56-3e2caf51b172)
```
df.info()
```
```
df.describe()
```
![image](https://github.com/user-attachments/assets/24c4cebe-9e8c-4e8b-adbc-d515e41bd34c)
```
df.shape
```
![image](https://github.com/user-attachments/assets/a2393f8c-aff3-43a2-bdd2-52aabd15926b)
```
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/020dfe7d-cd82-488c-9662-4af681a9283b)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/baa4c0f8-247b-4943-afd3-d4db4b5e40b7)
```
df.Pclass.unique()
```
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
```
sns.countplot(data=df,x="Survived")
```
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/36a003c7-dff6-4d4d-9a65-1efa3cdbdd8d)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
```
sns.jointplot(x="Age",y="Fare",data=df)
```
```
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
```
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![Uploading image.png…]()
```
sns.pairplot(df)
```
![Uploading image.png…]()

# RESULT
Thus, the Exploratory Data Analysis on the given data set was performed successfully.       
