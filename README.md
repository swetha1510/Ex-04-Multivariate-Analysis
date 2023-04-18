# Ex-04-Multivariate-Analysis

## AIM
To perform Multivariate Exploratory Data Analysis on the given data set.

EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM
STEP 1: Import the built libraries required to perform EDA and outlier removal.

STEP 2: Read the given csv file.

STEP 3: Convert the file into a dataframe and get information of the data.

STEP 4: Return the objects containing counts of unique values using (value_counts()).

STEP 5: Plot the counts in the form of Histogram or Bar Graph.

STEP 6: Use seaborn the bar graph comparison of data can be viewed.

STEP 7: Find the pairwise correlation of all columns in the dataframe.corr()

STEP 8: Save the final data set into the file.


## CODE
```
PROGRAM DEVELOPED BY : SWETHA P
REGISTER NUMBER : 212222100053
```

```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("/content/drive/MyDrive/Colab Notebooks/Semester 3/19AI403 _Intro to DS/Exp_3/SuperStore.csv")
df

df.head()

df.info()

df.describe()

df.tail()

df.shape

df.columns

df.isnull().sum()

df.duplicated()

df['Postal Code'] = df['Postal Code'].fillna(df['Postal Code'].mode()[0])

df.isnull().sum()

states=df.loc[:,["State","Sales"]]
states=states.groupby(by=["State"]).sum().sort_values(by="Sales")
plt.figure(figsize=(17,7))
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("STATES")
plt.ylabel=("SALES")
plt.show()

states=df.loc[:,["Segment","Sales"]]
states=df.groupby(by=["Segment"]).sum()
sns.barplot(x=states.index,y="Sales",data=states)
plt.xticks(rotation = 90)
plt.xlabel=("SEGMENT")
plt.ylabel=("SALES")
plt.show()

sns.barplot(df["Ship Mode"],df["Sales"],hue=df["Category"])

df.corr()
sns.heatmap(df.corr(),annot=True)

plt.figure(figsize=(10,7))
sns.scatterplot(df['Sub-Category'], df['Sales'], hue=df['Ship Mode'])
plt.xticks(rotation = 90)
```

## OUTPUT

## DATASET 
![ex04 dataset1](https://user-images.githubusercontent.com/120623583/232685615-9efa09ec-694a-496d-af2a-c5efe172928c.png)

## DATESET HEAD
![ex04datasethead2](https://user-images.githubusercontent.com/120623583/232685918-0ace1b40-1f76-45b9-a747-50d424a3d350.png)

## DATASET INFO
![ex04 dataeetinfo3](https://user-images.githubusercontent.com/120623583/232685986-1cd223fa-9b54-4358-81d6-3aacc0b3752f.png)

## DATASET DESCRIBE
![ex04datasetdecribe4](https://user-images.githubusercontent.com/120623583/232686056-3ea090be-26d8-4d59-9c5d-f5cb2f038b12.png)

## DATASET TAIL
![ex4datasettail5](https://user-images.githubusercontent.com/120623583/232686223-38619cd9-ce62-4742-a33c-1629e3ee83c7.png)

## DATASET SHAPE
![ex04datsetshape6](https://user-images.githubusercontent.com/120623583/232686302-ac231aba-2bb0-4399-9322-3220903e931c.png)

## DATASET COLUMN
![ex04datasetcolums7](https://user-images.githubusercontent.com/120623583/232686403-16638fa6-f40d-4df0-bdfc-1515a7c94439.png)

## NULL VALUE-PRE CLEANING
![ex4datasetnullvalues8](https://user-images.githubusercontent.com/120623583/232686607-10b14eaa-211b-46dc-ab1b-93811956b423.png)

## DATSET DUPLICATE
![ex04datsetduplicate9](https://user-images.githubusercontent.com/120623583/232686755-390f40bd-4128-4864-adb6-64c143eab9e3.png)

## NULL VALUE- POST CLEANING
![ex04nullvaluepost10](https://user-images.githubusercontent.com/120623583/232686844-d5b5e2a4-9dc6-4354-a8da-577477617b24.png)

## MULTIVARIATE - ANALYSIS STATE
![ex04multi1](https://user-images.githubusercontent.com/120623583/232687031-12b426d1-175b-4fff-8280-219ced71f8cf.png)

## MULTIVARIATE -ANALYSIS SEGMENT
![ex04multisegment2](https://user-images.githubusercontent.com/120623583/232687186-d561d9b4-5a3e-4daa-9704-e344cd0ec5ff.png)

## MULTIVARIATE -SHIP MODE & CATEGORY Vs SALES
![ex04multiship3](https://user-images.githubusercontent.com/120623583/232687405-71285ebf-7d0e-4f46-a69b-254ef67bdb46.png)

## MULTIVARIATE ANALYSIS - HEAT MAP
![ex4multiheatmap4](https://user-images.githubusercontent.com/120623583/232687548-8bf129c5-205c-4b2d-980c-dad490384a3d.png)

## MULTIVARIATE ANALYSIS - SUB CATEGORY & SHIP MODE Vs SALES



