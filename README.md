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
```
# Data.csv :
```
import pandas as pd
df=pd.read_csv("data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder,OneHotEncoder
import category_encoders as ce
be=ce.BinaryEncoder()
ohe=OneHotEncoder(sparse=False)
le=LabelEncoder()
oe=OrdinalEncoder()


df1["City"] = ohe.fit_transform(df1[["City"]])

temp=['Cold','Warm','Hot','Very Hot']
oe1=OrdinalEncoder(categories=[temp])
df1['Ord_1'] = oe1.fit_transform(df1[["Ord_1"]])

edu=['High School','Diploma','Bachelors','Masters','PhD']
oe2=OrdinalEncoder(categories=[edu])
df1['Ord_2']= oe2.fit_transform(df1[["Ord_2"]])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'City', 'Ord_1','Ord_2','Target'])
df5
```
# Encoding.csv :
```
import pandas as pd
df=pd.read_csv("Encoding Data.csv")
df

#feature generation
import category_encoders as ce
be=ce.BinaryEncoder()
ndf=be.fit_transform(df["bin_1"])
df["bin_1"] = be.fit_transform(df["bin_1"])
ndf

ndf2=be.fit_transform(df["bin_2"])
df["bin_2"] = be.fit_transform(df["bin_2"])
ndf2

df1=df.copy()
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
le=LabelEncoder()
oe=OrdinalEncoder()

df1["nom_0"] = oe.fit_transform(df1[["nom_0"]])
temp=['Cold','Warm','Hot']
oe2=OrdinalEncoder(categories=[temp])
df1['ord_2'] = oe2.fit_transform(df1[['ord_2']])

df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df0=pd.DataFrame(sc.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df0

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df2=pd.DataFrame(sc1.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df2

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df3=pd.DataFrame(sc2.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df3

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df4=pd.DataFrame(sc3.fit_transform(df1),columns=['id', 'bin_1', 'bin_2', 'nom_0','ord_2'])
df4
```
# Titanic.csv :
```
import pandas as pd
df=pd.read_csv("titanic_dataset.csv")
df

#removing unwanted data
df.drop("Name",axis=1,inplace=True)
df.drop("Ticket",axis=1,inplace=True)
df.drop("Cabin",axis=1,inplace=True)

#data cleaning
df.isnull().sum()

df["Age"]=df["Age"].fillna(df["Age"].median())
df["Embarked"]=df["Embarked"].fillna(df["Embarked"].mode()[0])

df.isnull().sum()

df

#feature encoding
from category_encoders import BinaryEncoder
be=BinaryEncoder()
df["Sex"]=be.fit_transform(df[["Sex"]])
ndf=be.fit_transform(df["Sex"])
ndf

df1=df.copy()
from sklearn.preprocessing import LabelEncoder, OrdinalEncoder
embark=['S','C','Q']
e1=OrdinalEncoder(categories=[embark])
df1['Embarked'] = e1.fit_transform(df[['Embarked']])
df1

#feature scaling
from sklearn.preprocessing import MinMaxScaler
sc=MinMaxScaler()
df2=pd.DataFrame(sc.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df2

from sklearn.preprocessing import StandardScaler
sc1=StandardScaler()
df3=pd.DataFrame(sc1.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df3

from sklearn.preprocessing import MaxAbsScaler
sc2=MaxAbsScaler()
df4=pd.DataFrame(sc2.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df4

from sklearn.preprocessing import RobustScaler
sc3=RobustScaler()
df5=pd.DataFrame(sc3.fit_transform(df1),columns=['Passenger','Survived','Pclass','Sex','Age','SibSp','Parch','Fare','Embarked'])
df5
```
# OUPUT

# Data.csv :
# Initial Dataset:

![image](https://user-images.githubusercontent.com/113497104/233391535-c3a209ab-9a23-4b60-ab8f-0bccf3b1d00c.png)

# Binary Encoding:
![image](https://user-images.githubusercontent.com/113497104/233391794-eb2b90bb-0a26-435a-8325-8cfae4cfe698.png)
![image](https://user-images.githubusercontent.com/113497104/233391832-6d2f1cf5-5579-4308-9e65-e77f0f943fc8.png)
 
 # Encoded Dataset:
 ![image](https://user-images.githubusercontent.com/113497104/233393533-6fa602c8-dd3f-4656-a65f-a6e92dcc5ee2.png)

# Data Scaling using MinMaxScaler:
![image](https://user-images.githubusercontent.com/113497104/233393692-72b443c5-9dd5-4309-b044-43a777d38aa6.png)

# Data Scaling using StandardScaler:
![image](https://user-images.githubusercontent.com/113497104/233393877-efa1069d-c7e0-4ba4-a995-9f9b28022b13.png)

# Data Scaling using MaxAbsScaler:
![image](https://user-images.githubusercontent.com/113497104/233394037-44dd28aa-ea59-49b2-a6c9-85515d1d7208.png)

# Data Scaling using RobustScaler:
![image](https://user-images.githubusercontent.com/113497104/233394166-a73b40b9-3018-4cfe-8213-ba23ff48bf4b.png)

# Encoding.csv :
# Initial Dataset:
![image](https://user-images.githubusercontent.com/113497104/233394342-bd9fee7e-888e-4ec8-a83e-2a86ec3ad003.png)

# Binary Encoding:
![image](https://user-images.githubusercontent.com/113497104/233394533-78e4002c-c172-4382-9a41-a86c13b5f944.png)
![image](https://user-images.githubusercontent.com/113497104/233394582-155a22a9-5194-4bf1-96f4-b081c3abea37.png)

# Encoded Dataset:
![image](https://user-images.githubusercontent.com/113497104/233394769-700b8489-7dbc-413b-bbba-017f4c2288ca.png)

# Data Scaling using MinMaxScaler:
![image](https://user-images.githubusercontent.com/113497104/233394928-45f0387c-ff2e-4b84-bb8c-1c63c1f4722b.png)

# Data Scaling using StandardScaler:
![image](https://user-images.githubusercontent.com/113497104/233395068-24df53ec-0f74-4e9a-b98c-7a736a9f305c.png)

# Data Scaling using MaxAbsScaler:
![image](https://user-images.githubusercontent.com/113497104/233395191-b793868f-9fc3-43c2-914b-8a82157f0c7e.png)

# Data Scaling using RobustScaler:
![image](https://user-images.githubusercontent.com/113497104/233395497-0b2ffc8b-880b-4ae5-8b51-b0617361a4c2.png)

# Titanic.csv :
# Initial Dataset:
![image](https://user-images.githubusercontent.com/113497104/233395645-857aab2a-15e7-4a7a-a0e1-2e7a4180b073.png)

# Data cleaning before encoding:
![image](https://user-images.githubusercontent.com/113497104/233395773-a5e13996-9ecc-4173-8d82-df8ff1e2c3e4.png)

# Cleaned Dataset:
![image](https://user-images.githubusercontent.com/113497104/233395904-b9cc1adc-bac2-4d68-8a44-96fc4946264f.png)

# Binary Encoding:
![image](https://user-images.githubusercontent.com/113497104/233396090-f151e3bb-b3a2-4c47-a4a0-9a1023843192.png)

# Encoded Dataset:
![image](https://user-images.githubusercontent.com/113497104/233396208-38853452-f8c9-444a-b7b1-0ca73e2e9665.png)

# Data Scaling using MinMaxScaler:
![image](https://user-images.githubusercontent.com/113497104/233396336-23ccab63-897f-4f03-87da-5ffd1817bcad.png)

# Data Scaling using StandardScaler:
![image](https://user-images.githubusercontent.com/113497104/233396702-fa24dee0-a06b-4f56-9e6f-562d1b53c9c2.png)

# Data Scaling using MaxAbsScaler:
![image](https://user-images.githubusercontent.com/113497104/233397085-006a1632-0c4f-40b9-b015-7bcc9d9e4f99.png)

# Data Scaling using RobustScaler:
![image](https://user-images.githubusercontent.com/113497104/233397749-6346aabb-1887-4a83-a8eb-b9ead3bf1208.png)

# RESULT:

Feature Generation process and Feature Scaling process is applied to the given data frames sucessfully.
