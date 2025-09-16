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
Univariate Analysis
```

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv('/content/titanic_dataset (1).csv')
df
```

<img width="1377" height="626" alt="ds2 1" src="https://github.com/user-attachments/assets/0585d691-e1d8-4e0a-b41b-a2f101676c0d" />

```
df.info()
```

<img width="807" height="430" alt="ds2 2" src="https://github.com/user-attachments/assets/1d4b807a-bfb4-4711-8735-94fca36945c2" />

```
df.dtypes
```

<img width="1207" height="565" alt="ds2 3" src="https://github.com/user-attachments/assets/79e2e9d8-0adf-48b7-97a0-ea125c7e26e6" />

```
df.describe()
```

<img width="1355" height="381" alt="ds2 4" src="https://github.com/user-attachments/assets/dc570995-f8d2-428b-9dea-a4e10689f555" />

```
df["Age"].value_counts()
```

<img width="1032" height="588" alt="ds2 5" src="https://github.com/user-attachments/assets/18a3f18f-766e-4aba-a3fa-89595e1bb9dd" />

```
df.shape
```

<img width="607" height="87" alt="ds2 6" src="https://github.com/user-attachments/assets/f71c63d7-f8df-4ba8-b6d7-6fdba7523dba" />

```
df.set_index("PassengerId",inplace=True)
df.describe()
```

<img width="966" height="402" alt="ds2 7" src="https://github.com/user-attachments/assets/a776b904-f1fb-4454-8248-e5cc877426ef" />

```
df.nunique()
```

<img width="875" height="525" alt="ds2 8" src="https://github.com/user-attachments/assets/3fd3ebd6-095f-4a01-824c-c2f1e66dc2e1" />

```
sns.countplot(data=df,x="Survived")
```

<img width="1298" height="567" alt="ds2 9" src="https://github.com/user-attachments/assets/2f857e99-c203-45c4-8ff0-d23c214a4c72" />

```
df.Pclass.unique()
```

<img width="625" height="85" alt="ds2 10" src="https://github.com/user-attachments/assets/2164754e-1d4a-463a-bb26-d8de0cdbad89" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1538" height="580" alt="ds2 11" src="https://github.com/user-attachments/assets/74b27a7b-e48c-4d05-ab99-53a9f14ce205" />

```
Bivariate Analysis
```

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

<img width="1391" height="693" alt="ds2 12" src="https://github.com/user-attachments/assets/b0f31e28-e9e2-4993-9873-2f840433ce66" />

```
df.boxplot(column="Age",by="Survived")
```

<img width="975" height="602" alt="ds2 13" src="https://github.com/user-attachments/assets/176c2a48-cde1-4169-97af-ed3f2dc190e4" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```

<img width="978" height="571" alt="ds2 14" src="https://github.com/user-attachments/assets/8df6fdfa-8062-4146-a363-1235848fde61" />

```
Multivariate Analysis
```

```
fig, ax1 = plt.subplots(figsize=(10,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="1437" height="643" alt="ds2 15" src="https://github.com/user-attachments/assets/74c16676-a89b-4cab-b42f-86a9261104d1" />

```
#fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```

<img width="1232" height="573" alt="ds2 16" src="https://github.com/user-attachments/assets/a6541db6-00b3-4c79-a61b-fd8f9c1cadb1" />

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

<img width="1473" height="636" alt="ds2 17" src="https://github.com/user-attachments/assets/80b48b9c-fb61-4d9d-805f-b9bf0d84cb52" />

```
corr = df.select_dtypes(include=np.number).corr()
sns.heatmap(corr, annot=True)
```

<img width="1358" height="575" alt="ds2 18" src="https://github.com/user-attachments/assets/b997a76c-51f1-4546-8d87-a9d4e0b9914e" />














# RESULT
        To perform Exploratory Data Analysis on the given data set is successfully completed.
