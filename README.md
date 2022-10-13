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
~~~
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

~~~
# OUPUT
![image](https://user-images.githubusercontent.com/113016903/195489654-df2148d0-dd40-4fb2-aa51-8a4e99cb3284.png)
![image](https://user-images.githubusercontent.com/113016903/195489748-d9ff640f-6efa-4499-8190-a72c5a7ee3cb.png)
![image](https://user-images.githubusercontent.com/113016903/195489782-0eb18311-5999-4462-8fb2-e0c5e1346ff2.png)
![image](https://user-images.githubusercontent.com/113016903/195489814-4d642e32-2f2b-4c89-a024-260f09d1b44f.png)
![image](https://user-images.githubusercontent.com/113016903/195490232-423bed9f-77ea-40cc-873e-c2a885416f09.png)
![image](https://user-images.githubusercontent.com/113016903/195490261-b1f12768-e832-48e5-a416-79c239167641.png)
![image](https://user-images.githubusercontent.com/113016903/195490300-7b475f4a-11c3-41ec-929f-162508b97748.png)
![image](https://user-images.githubusercontent.com/113016903/195491110-cf62fade-77b2-4c5b-a79d-e555e0ab8eac.png)
![image](https://user-images.githubusercontent.com/113016903/195491439-54fcd068-5d67-44d4-88ad-5edb9ecc84af.png)
![image](https://user-images.githubusercontent.com/113016903/195492130-ef2a6366-fe33-4a84-a858-8b4e28f493f8.png)
![image](https://user-images.githubusercontent.com/113016903/195492611-d855a499-c264-4255-984f-134d829d4506.png)
![image](https://user-images.githubusercontent.com/113016903/195493107-cccdd89b-7112-4632-aec6-0efdef3cae38.png)
![image](https://user-images.githubusercontent.com/113016903/195493284-ab63a0e3-f056-4d82-9954-0b8031cec4a9.png)
![image](https://user-images.githubusercontent.com/113016903/195494038-4f3a24f0-f1ab-4bad-b5ea-55b819ad0f77.png)
![image](https://user-images.githubusercontent.com/113016903/195494334-2f58552d-04db-4ff9-aa8f-7581e27ad12d.png)
![image](https://user-images.githubusercontent.com/113016903/195494484-20663ea4-6529-480e-9ea7-64d6e405fd7c.png)


