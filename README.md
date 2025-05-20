# SKILL ASSESSMENT - 2
```
NAME : P JANARDHAN
REGISTER NUMBER : 212224040128
```

# AIM :
To perform data preprocessing, detect and remove outliers using Boxplot and IQR methods, and carry out univariate and multivariate analysis using Count Plot and Distribution Plot on the Toyota car dataset.

# EQUIPMENTS REQUIRED :
1.Hardware – PCs

2.Software – Anaconda (Python 3.7) / Jupyter Notebook

# ALGORITHM :
1.Import necessary libraries – pandas, matplotlib, seaborn, numpy.

2.Load the dataset (Toyota.csv) and preview the data.

3.Perform data cleaning –

-Drop null values if any.

-Remove duplicates if present.

-Check for inconsistencies or irrelevant columns.

4.Detect Outliers using Boxplot Method –

-Plot boxplots for numerical columns like Price, Age, KM, etc.

-Visually inspect and identify outliers.

5.Remove Outliers using IQR Method –

-Calculate Q1, Q3, and IQR for each numeric feature.

-Remove rows where values fall below (Q1 - 1.5 * IQR) or above (Q3 + 1.5 * IQR).

6.Perform Univariate Analysis using Count Plot –

-Use seaborn.countplot() for categorical variables like FuelType.

7.Perform Multivariate Analysis using Dist Plot –

-Use sns.histplot() with hue parameter for comparing numerical features across categories.

# PROGRAM / OUTPUT :
```
Program Developed by : P JANARDHAN
Register Number : 212224040128
```
```
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np
df=pd.read_csv("Toyota.csv")
df
```
![435593021-e516315a-dae2-40d1-97d8-25bcdc7ca4a1](https://github.com/user-attachments/assets/5bd374f5-1647-45e3-805d-c34c3dc72dbc)
```
df.isnull().sum()
```
![435593680-576b3226-8a9a-4b2f-b5cf-254e2967740e](https://github.com/user-attachments/assets/00281b3d-3fdb-4048-a9bd-b00dfeff1fc0)

```
df.drop(columns=["Unnamed: 0"], inplace=True)
df.isna().sum()
```
![435594376-50518641-e8d6-46f5-9fb1-c7536d1e0821](https://github.com/user-attachments/assets/310cdba5-585f-49f2-9bda-5a4916023421)

```
df.dtypes
```
![435595045-32975efd-c97e-4e21-9b59-e666c3eb076e](https://github.com/user-attachments/assets/a6200b58-286a-409c-99dd-be3edccb5204)
```
df.columns()
```
![435595575-c998f32a-79ad-4f9a-85b6-75da799ac694](https://github.com/user-attachments/assets/3e12eb36-3da1-492a-95ad-4c9bb8c7f80f)
```
df = df.dropna()
```
![435596435-1fc63e6b-58b4-446b-bac1-bf28e21becb6](https://github.com/user-attachments/assets/50684f7f-35cc-4dd7-8977-4b095bd7666f)

```
df = df.drop_duplicates()
```
![435596784-b5d85b33-55ea-40fd-a84d-cfad887fe8ed](https://github.com/user-attachments/assets/f01a275e-f99a-49e7-8e03-5a6bbdcd6d3b)
## BOXPLOT METHOD :
```
plt.figure(figsize=(15, 5))
sns.boxplot(y=df['Price'], color='cyan')
plt.title("Boxplot - Price")
plt.show()
```
![435599102-e90736d1-5f9c-46fe-8373-93708af113ae](https://github.com/user-attachments/assets/b3e34e87-24fe-4cbb-8050-270484bb67c7)

```
sns.boxplot(y=df['Age'], color='purple')
plt.title("Boxplot - Age")
plt.show()
```
![435599102-e90736d1-5f9c-46fe-8373-93708af113ae](https://github.com/user-attachments/assets/aceb6a4c-b247-4cd1-b0c5-1d4ad65975a0)

```
sns.boxplot(y=df['Age'], color='purple')
plt.title("Boxplot - Age")
plt.show()
```
![435599432-2ecbf1fc-a251-46c0-9bd1-32a81741035a](https://github.com/user-attachments/assets/34770529-b79c-4043-ae28-2de0299e9669)

```
sns.boxplot(y=df['KM'], color='yellow')
plt.title("Boxplot - KM")
plt.show()
```
![435599792-1f10266f-d580-4d83-8cf6-d815d22170cf](https://github.com/user-attachments/assets/b0e39272-6eba-4d1d-bb16-830d585dd234)

## IQR METHOD :
```
def remove_outliers_iqr(data, column):
    Q1 = data[column].quantile(0.25)
    Q3 = data[column].quantile(0.75)
    IQR = Q3 - Q1
    lower = Q1 - 1.5 * IQR
    upper = Q3 + 1.5 * IQR
    return data[(data[column] >= lower) & (data[column] <= upper)]

df = remove_outliers_iqr(df, 'Price')
df = remove_outliers_iqr(df, 'Age')
df = remove_outliers_iqr(df, 'KM')
```
![435600721-3de34be7-be03-4829-82e4-20624984ea56](https://github.com/user-attachments/assets/722294e4-bce9-4e3b-8194-46c3856ee793)
## COUNT PLOT
```
plt.figure(figsize=(6, 4))
sns.countplot(x='FuelType', data=df, palette='Set2')
plt.title("Count Plot - Fuel Type")
plt.show()
```
![435601128-1433572c-4e14-471a-8e6c-45bb08506606](https://github.com/user-attachments/assets/ee404d96-b60a-41d1-86a1-30a77c7f6726)

## DISPLOT:
```
plt.figure(figsize=(10, 6))
sns.histplot(data=df, x='Price', hue='FuelType', kde=True, palette='husl')
plt.title("Distribution Plot of Price by Fuel Type")
plt.show()
```
![435601511-48ba8cd7-0c64-4152-89db-4c399d1f8e1e](https://github.com/user-attachments/assets/a405033e-c4cb-4e51-a2b5-176266ef3bdf)

# RESULT :

The program was successfully executed. Data was cleaned, outliers were detected and removed using boxplot and IQR methods, and both univariate and multivariate analyses were performed using count plot and distplot.
