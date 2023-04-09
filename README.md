### workshop-Multivariate-analysis
### AIM:
To perform Bivariate/Multivariate Analysis for the given data set.

### ALGORITHM:
### Step1
Read the given data.

### Step2
Get information from the data.

### Step3
Perform the Multivariate Analysis.

### Step4
Save the cleaned data.

###PROGRAM:
```
DEVELOPED BY:D.Vinitha
REGISTRATION NUMBER: 212222230175

import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
datas=pd.read_excel(r"/content/FlightInformation.xlsx")
df=pd.DataFrame(datas)
df
df.info()
df.head()
df.isnull().sum()
#Data cleaning
df['Route']=df['Route'].fillna(df['Route'].mode()[0])
df['Total_Stops']=df['Total_Stops'].fillna(df['Total_Stops'].mode()[0])
df.isnull().sum()
#NUMERICAL AND NUMERICAL
sns.scatterplot(x=df['Destination'],y=df['Price'])
sns.scatterplot(x=df['Destination'],y=df['Total_Stops'])
#NUMERICAL AND CATEGORICAL
sns.barplot(x=df["Source"],y=df["Price"],data=df)
sns.barplot(x=df['Source'],y=df['Price'],hue=df['Destination'])
DEST=df.loc[:,["Destination","Price"]]
DEST=DEST.groupby(by=["Destination"]).sum().sort_values(by="Price")
plt.figure(figsize=(7,7))
sns.barplot(x=airline.index,y="Price",data=DEST)
plt.xticks(rotation = 90)
plt.xlabel=("DESTINATION")
plt.ylabel=("PRICE")
plt.show()
sns.boxplot(x=df['Price'],y=df['Duration'])
sns.displot(df, x="Source", hue="Airline")
#MULTIVARIATE ANALYSIS 
df.corr()
sns.heatmap(df.corr(),annot=True)

```
### OUTPUT:
### df.head()
![Screenshot 2023-04-09 222335](https://user-images.githubusercontent.com/121166004/230785876-38bed506-4f84-4922-89be-f207cf9f4a97.png)

### df.isnull().sum()
![Screenshot 2023-04-09 222343](https://user-images.githubusercontent.com/121166004/230785927-2d322096-a227-40c7-abab-f28b248656db.png)


### After cleaning
### df.isnull().sum()
![Screenshot 2023-04-09 222351](https://user-images.githubusercontent.com/121166004/230785973-b890dab4-1588-4346-92a1-80f31522bbf7.png)


### Numerical & Numerical
### scatter plot
![Screenshot 2023-04-09 222407](https://user-images.githubusercontent.com/121166004/230786013-4d251730-7d36-4d24-b7b3-e85394a1a7fb.png)
![Screenshot 2023-04-09 222415](https://user-images.githubusercontent.com/121166004/230786024-ffbde61d-e1e3-4802-8ec4-406205941b1a.png)


### Numerical & Categorical
### Barplot
![Screenshot 2023-04-09 222425](https://user-images.githubusercontent.com/121166004/230786057-eec427f5-0868-4038-a3f7-102096efba78.png)
![Screenshot 2023-04-09 222434](https://user-images.githubusercontent.com/121166004/230786070-bd280ef8-549f-4afd-a903-17145b3552ed.png)
![Screenshot 2023-04-09 222450](https://user-images.githubusercontent.com/121166004/230786094-56304853-9683-4dd0-ac1f-5f4dbb21363f.png)


### Boxplot
![Screenshot 2023-04-09 222507](https://user-images.githubusercontent.com/121166004/230786124-84476f59-6231-4595-868b-826b1ed7fed2.png)


### Distplot
![Screenshot 2023-04-09 222516](https://user-images.githubusercontent.com/121166004/230786208-bc907b93-2105-4da7-8ab2-47682b47773a.png)


### Multivariate Analysis
### Heatmap
![Screenshot 2023-04-09 222533](https://user-images.githubusercontent.com/121166004/230786219-da9235ce-728c-4d8d-966b-9a4ff8560995.png)


### RESULT
Thus the Bivariate/Multivariate Analysis for the given data set is executed successfully.
