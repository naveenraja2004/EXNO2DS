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
## name:N.R NAVEEN RAJA
## reg no:212222230093
```
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```

![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/f77a2404-c9b8-44c7-ba01-599200fa1147)
```
dt.info()
```

![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/3a577d9f-603c-4d7f-8139-e6c72bed9d13)
```
dt.shape
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/8991d428-cdd2-443c-8078-b4346f4cc322)
```
dt.set_index("PassengerId",inplace=True
```

![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/5f777cd7-b4bf-4205-bd4d-c8e7129df71b)
```
dt.nunique()
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/cbf00a99-302e-4d07-adfc-654dd2a0ddf3)
```
dt["Survived"].value_counts()
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/2cad5b3f-e7cb-40c7-b5dd-aa3ce0a24075)
```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/5219ba21-a67a-47d2-8748-bb9f9062bc32)
```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/38fbaa01-6ea6-479e-8ca6-123c70d36104)
```
dt
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/b1889806-eafd-44c8-b06e-afe4e07dbacf)
```
dt.Pclass.unique()
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/d3a77afb-df27-4873-871f-cb0bcda67d0f)
```
dt.rename(columns={'Sex':'Gender'},inplace=True)
dt
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/abafd819-f22d-4ea1-8837-8d6a9704703d)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5, aspect=.7)
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/439b5e9a-b97c-4c06-9bde-bc25f380bff7)
```
sns.catplot(x='Survived',hue="Gender",data=dt,kind="count")
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/e0e16968-e2d7-4d45-ace9-cf90f9ff03f1)
```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/bb51975b-955b-420b-b4d4-cc2162832753)
```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/fff67187-e7cd-448f-b635-8f7e47a6144c)
```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/49e84a2a-06b4-4eed-a4ca-59252bf195d5)
```
import matplotlib.pyplot as plt
fig, ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=dt)
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/8896edd6-0750-49ea-9c0b-e8c760d190c5)
```
sns.catplot(data=dt,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/ca363de7-cedd-4b52-a794-3f5f9fea5ea2)
```
#co-relation
import seaborn as sns
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/25eb13f2-4d89-4c46-8f14-f05183088193)
```
sns.pairplot(dt)
```
![image](https://github.com/hashish9275/EXNO2DS/assets/118707521/7a4a643a-8d14-4f1a-afc9-c043473f7b37)

# RESULT
```
The code successfully excuted
```
