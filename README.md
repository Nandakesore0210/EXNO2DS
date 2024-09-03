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
dt=pd.read_csv("titanic_dataset.csv")
dt
```
![image](https://github.com/user-attachments/assets/c4971a16-09a9-4d2f-91bb-ac1c29c75a84)

## dt.info()
![image](https://github.com/user-attachments/assets/e0b52f22-a814-44b5-8fdb-41db3745d30e)

## dt.describe()
![image](https://github.com/user-attachments/assets/5c5c81f8-27f5-4c67-bc15-33b4b532965f)

## dt.nunique()
![image](https://github.com/user-attachments/assets/edf5869b-e8c8-489c-a08f-db7f6bccc055)

## dt["Survived"].value_counts()
![image](https://github.com/user-attachments/assets/7ce8d2a3-113c-49c7-b405-042483a77e25)

## per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
![image](https://github.com/user-attachments/assets/5df49aa7-349b-47a3-9b6b-ebf11ecf081b)

## sns.countplot(data=dt,x="Survived")
![image](https://github.com/user-attachments/assets/98aa8112-788b-4e3f-8215-a0aacc3026fa)

## dt.Pclass.unique()
![image](https://github.com/user-attachments/assets/330d4ebc-658e-4f83-a6c7-19663c38d2f3)

## dt.rename(columns={'Sex':'Gender'},inplace=True)
![image](https://github.com/user-attachments/assets/e59be3d9-5b94-4ab9-b127-35ccfbd261b3)

## sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
![image](https://github.com/user-attachments/assets/6f66471c-0cd9-4a31-80c9-ed68c31bded2)

## sns.catplot(x="Survived",hue="Gender",data=dt,kind="count")
![image](https://github.com/user-attachments/assets/142f3afc-8986-419e-b96e-0168e5f2c576)

## dt.boxplot(column="Age",by="Survived")
![image](https://github.com/user-attachments/assets/3481b2e8-a2ab-4ff9-abfc-d918306c2151)

## sns.scatterplot(x=dt["Age"],y=dt["Fare"])
![image](https://github.com/user-attachments/assets/6316f0d7-e877-423e-9770-16668e5f37cb)

## sns.jointplot(x="Age",y="Fare",data=dt)
![image](https://github.com/user-attachments/assets/f1fdc309-5b81-4e79-a8ae-e435461beefa)

## sns.catplot(x="Gender",col="Survived",hue="Pclass",kind="count",data=dt)
![image](https://github.com/user-attachments/assets/b39471cb-db19-471e-9a74-5352a0d039c1)

```
dr=dt.select_dtypes(exclude=[object])
corr=dr.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/4078f41e-5062-493e-809a-7423be6a0e74)

## sns.pairplot(dt)
![image](https://github.com/user-attachments/assets/1b327ea5-5339-4645-b512-80a7d02ab285)

# RESULT
Thus the data analysis has been implemented succesfully.
