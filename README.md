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
## OUTPUT
<img width="1348" height="779" alt="Screenshot 2025-10-04 143926" src="https://github.com/user-attachments/assets/ec72a804-2a8a-4d89-a1b3-bb5b9864f674" />

```
 df.info()
```
## OUTPUT
<img width="1040" height="477" alt="Screenshot 2025-10-04 143936" src="https://github.com/user-attachments/assets/97b96059-7c8a-41e0-a38e-6d9885a3a72f" />

```
 df.describe()
```
## OUTPUT
<img width="1121" height="420" alt="Screenshot 2025-10-04 143944" src="https://github.com/user-attachments/assets/762027ad-e7e6-48a0-b5f5-be6821608cb2" />

```
df.dtypes
```
## OUTPUT
<img width="1183" height="627" alt="Screenshot 2025-10-04 143954" src="https://github.com/user-attachments/assets/4be765e2-7bc3-4f38-961b-c8b1b5391db4" />

```
 df.shape
```
## OUTPUT
<img width="949" height="96" alt="Screenshot 2025-10-04 144004" src="https://github.com/user-attachments/assets/ceffffd9-4dd8-4caa-ad28-8156804bc0cf" />

```
 df.value_counts()
```
## OUTPUT
<img width="1396" height="764" alt="Screenshot 2025-10-04 144014" src="https://github.com/user-attachments/assets/12240b2e-f58d-4129-a314-70f0fd089c6e" />

```
 df['Age'].value_counts()
```
## OUTPUT
<img width="1233" height="662" alt="Screenshot 2025-10-04 144024" src="https://github.com/user-attachments/assets/4b27e1db-3a61-4f62-98a2-65038f1243bd" />

```
df.set_index("PassengerId", inplace=True)
df
```
## OUTPUT
<img width="1399" height="697" alt="Screenshot 2025-10-04 144033" src="https://github.com/user-attachments/assets/cd296894-fd67-46bf-aaff-243eb4b04eb4" />

```
 df.nunique()
```
## OUTPUT
<img width="1249" height="585" alt="Screenshot 2025-10-04 144045" src="https://github.com/user-attachments/assets/41d97adf-45cd-4fb7-9af2-a3063f18fd22" />

```
sns.countplot(data=df,x='Survived')
```
## OUTPUT
<img width="1088" height="630" alt="Screenshot 2025-10-04 144054" src="https://github.com/user-attachments/assets/7b5fc92d-6059-4e83-9007-8dc7b5f6f7db" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
## OUTPUT
<img width="1394" height="708" alt="Screenshot 2025-10-04 144107" src="https://github.com/user-attachments/assets/badb3ee2-ac1c-43ee-8605-75c85f34b6a0" />

```
 sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
## OUTPUT
<img width="1149" height="706" alt="Screenshot 2025-10-04 144116" src="https://github.com/user-attachments/assets/728c500d-103a-435f-b4cd-c98da220c002" />

```
df.boxplot(column="Age",by="Survived")
```
## OUTPUT
<img width="1195" height="669" alt="Screenshot 2025-10-04 144125" src="https://github.com/user-attachments/assets/76ef0fac-72dc-4918-ae36-23a93d446e35" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
## OUTPUT
<img width="1100" height="636" alt="Screenshot 2025-10-04 144135" src="https://github.com/user-attachments/assets/aef97285-dbc7-48cc-ae41-9d4d81886bcb" />

```
 fig, axl=plt.subplots(figsize=(8,5))
 plt=sns.boxplot(ax=axl,x='Pclass',y='Age',hue='Gender',data=df)
```
## OUTPUT
<img width="1169" height="651" alt="Screenshot 2025-10-04 144145" src="https://github.com/user-attachments/assets/33621ee0-5696-4aa1-b695-b5e4391dec94" />

```
 plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
## OUTPUT
<img width="1040" height="633" alt="Screenshot 2025-10-04 144153" src="https://github.com/user-attachments/assets/86fe4a12-4ccf-48d5-be7a-2ecca28da156" />

```
import seaborn as sns
sns.catplot(x='Pclass',y="Age",hue="Gender",col="Survived",kind="box",data=df)
```
## OUTPUT
<img width="1405" height="729" alt="Screenshot 2025-10-04 144203" src="https://github.com/user-attachments/assets/5890d207-958a-4383-8518-bdb34344ff68" />

```
 sns.catplot(data=df,col="Survived",x="Gender",hue='Pclass',kind="count")
```
## OUTPUT
<img width="1408" height="710" alt="Screenshot 2025-10-04 144212" src="https://github.com/user-attachments/assets/ba4aae07-632e-48b3-94eb-40838ff07968" />

```
 corr=df.corr(numeric_only=True)
 sns.heatmap(corr,annot=True)
```
## OUTPUT
<img width="1215" height="638" alt="Screenshot 2025-10-04 144220" src="https://github.com/user-attachments/assets/9dab5e07-27de-4af2-9535-da4d9f69f3fe" />

```
corr=df.select_dtypes(include=np.number).corr()
sns.heatmap(corr,annot=True)
```
## OUTPUT
<img width="1346" height="630" alt="Screenshot 2025-10-04 144231" src="https://github.com/user-attachments/assets/0e93d407-dd39-440c-b462-9380c4b6d0fd" />

# RESULT

 Thus the programs are executed successfully.
