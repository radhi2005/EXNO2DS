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
DEVELOPED BY : RADHIMEENA M
REG NO : 212223040159
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/8a494c11-4fcd-4f68-974c-1aa6c32b9674)
```
df.head(10)
```
![image](https://github.com/user-attachments/assets/410e8893-089d-405f-abc0-9e3860442812)
```
df.tail(10)
```
![image](https://github.com/user-attachments/assets/c17a8e92-6081-455d-9e4c-a6e1a9da41ca)
```
df.info()
```
![image](https://github.com/user-attachments/assets/ecf3a916-1701-405a-9ee5-b99bc2459e06)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/80e9dcb5-d470-49fd-854e-f17c8c3fa694)
```
df.shape
```
![image](https://github.com/user-attachments/assets/194fe4b7-24fb-400d-91c2-d3a84dd1f636)
```
df.set_index("PassengerId",inplace=True)
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/992661f7-9891-48be-808e-ef410dbb06c2)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/5b20ddb6-92e1-4fc7-a173-01742bfd0b5f)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/8f0cba25-2a09-4c41-9f6e-a198754898b7)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/b50197c6-9e95-4793-8287-60f244e5a149)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/d2cb3e08-2fc5-424d-8e42-3ac4a4015b54)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/d4cffe2b-6036-45e7-ab2e-f5c47f987491)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5)
```
![image](https://github.com/user-attachments/assets/6012c417-c3fb-4b62-9cd5-1584416e971e)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/1f405276-bc96-4ce5-9be7-3eca181b07c4)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/adccd2d6-b71c-4c03-9794-2473ced42d1d)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/4191da3e-e79f-45a5-be36-9dd3fa54d696)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/7487d113-b688-49ae-8386-d673dcee7216)
```
fig,ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x="Pclass",y="Age",hue="Gender",data=df)
```
![image](https://github.com/user-attachments/assets/7e668b6e-622f-4402-bde9-556b76c8e22d)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/b8113af6-3ab9-426d-8d0b-6a9bf7b9a157)
```
## Co-relation
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/f18344e3-7639-4bf7-8d05-bac3a4fb67e9)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/2a46b4b9-9129-4a27-9e5a-261ea91029ee)

# RESULT
        Thus, the Exploratory Data Analysis on the given data set was performed successfully.
