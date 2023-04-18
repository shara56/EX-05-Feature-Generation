# EX-05-Feature-Generation


## AIM
To read the given data and perform Feature Generation process and save the data to a file. 

# Explanation
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.
 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature Generation techniques to all the feature of the data set
### STEP 4
Save the data to the file


# CODE
```
NAME: SHARANGINI T K
REG NO: 212222230143

import pandas as pd

df=pd.read_csv("/content/data[1].csv")

df.info()

df.isnull().sum()

from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()

df['Ord_2'] = le.fit_transform(df['Ord_2'])

sns.set(style ="darkgrid")

sns.countplot(df['Ord_2'])

from sklearn.preprocessing import OneHotEncoder

enc = OneHotEncoder()

enc = enc.fit_transform(df[['City']]).toarray()

encoded_colm = pd.DataFrame(enc)

df = pd.concat([df, encoded_colm], axis=1)

df = df.drop(['City'], axis=1)

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_2'], columns=['Ord_2'])

df.head(10)

df = pd.get_dummies(df, prefix=['Ord_1'], columns=['Ord_1'])

df.head(10)
```

# OUPUT

![image](https://user-images.githubusercontent.com/113497104/232683485-0559b4a5-c359-4235-adc6-1b061427a3e6.png)

![image](https://user-images.githubusercontent.com/113497104/232683540-cebc25a1-7d56-4c3e-9fce-b708bfac4dc8.png)

![image](https://user-images.githubusercontent.com/113497104/232683612-13bf5fbd-b7d0-43c5-861a-c16b4b737bab.png)

![image](https://user-images.githubusercontent.com/113497104/232683663-eb1e7bb9-f32a-40fc-89c4-8a47c7219278.png)

![image](https://user-images.githubusercontent.com/113497104/232683686-253b5fe9-54bf-414e-b082-af972ad67bb7.png)

## Encoding dataset

![image](https://user-images.githubusercontent.com/113497104/232683963-d3423d24-6a9e-4e45-adbc-becfa294ab10.png)

![image](https://user-images.githubusercontent.com/113497104/232684022-08172b90-0a8d-45c0-8587-ba43a7b77b25.png)

![image](https://user-images.githubusercontent.com/113497104/232684054-ecd4fee6-179c-440c-a412-71cf16300d76.png)

![image](https://user-images.githubusercontent.com/113497104/232684089-d1cd04f6-8903-4f6e-9f6e-9dfb51ffdd7d.png)

![image](https://user-images.githubusercontent.com/113497104/232684125-666907c2-d872-4259-bdc4-aac15a0d451c.png)

![image](https://user-images.githubusercontent.com/113497104/232684144-6d685cc8-3f7b-4cda-b918-827db578a0e4.png)

![image](https://user-images.githubusercontent.com/113497104/232684243-c89258d7-cfea-4c43-94ef-f0609425187a.png)

![image](https://user-images.githubusercontent.com/113497104/232684269-1f5a7baf-bbdc-42ab-adf7-60fd6ffbc480.png)

![image](https://user-images.githubusercontent.com/113497104/232685661-b9907d70-e56a-4561-8cfa-59cff52ccc52.png)

![image](https://user-images.githubusercontent.com/113497104/232685700-0aa58331-d861-479e-b146-cc094caa0504.png)

![image](https://user-images.githubusercontent.com/113497104/232685739-3f172d1e-b28d-4371-bb32-919dfee8729f.png)

## RESULT

Hence Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.

