# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as pd
df=pd.read_csv("/content/SAMPLEIDS.csv")
df
<img width="1045" height="846" alt="Screenshot 2025-09-09 101254" src="https://github.com/user-attachments/assets/51cc6a1d-5de2-49a8-8dfa-a20ad99e7d90" />

df.head()
<img width="976" height="234" alt="Screenshot 2025-09-09 101501" src="https://github.com/user-attachments/assets/6960da4d-7bc3-439e-ac49-071e036fc6b7" />

df.tail()
<img width="1009" height="250" alt="Screenshot 2025-09-09 101616" src="https://github.com/user-attachments/assets/d6a97bdf-4fd0-4d74-ad9e-f6f02ac487d6" />

df.head(3)
<img width="952" height="166" alt="Screenshot 2025-09-09 101719" src="https://github.com/user-attachments/assets/0e9c820c-af42-4251-b93c-719f0d2db38a" />

df.tail(2)
<img width="972" height="129" alt="Screenshot 2025-09-09 102054" src="https://github.com/user-attachments/assets/381398f2-16f3-433b-9fda-9b544a7c3b64" />

df.isnull()

<img width="811" height="839" alt="Screenshot 2025-09-09 102230" src="https://github.com/user-attachments/assets/f2b0900c-8b43-48f1-9186-90324510f142" />

df.isnull().sum()
<img width="1441" height="560" alt="Screenshot 2025-09-12 212629" src="https://github.com/user-attachments/assets/23c9c78d-5cd7-49b5-bb0f-9dd49df7ad88" />

df.isnull().any()
<img width="1062" height="557" alt="Screenshot 2025-09-12 212738" src="https://github.com/user-attachments/assets/a15bb37d-60b1-46b4-ac7c-39f6172fb741" />

df.dropna(axis=0)

<img width="1028" height="531" alt="Screenshot 2025-09-12 212848" src="https://github.com/user-attachments/assets/ac280828-41aa-4033-b0cf-ba5769098806" />

df.dropna(axis=1)

<img width="460" height="838" alt="Screenshot 2025-09-12 213315" src="https://github.com/user-attachments/assets/095a1707-d4d7-4d71-acc7-26878064ee8d" />


df.fillna(5)

<img width="1063" height="840" alt="Screenshot 2025-09-12 213452" src="https://github.com/user-attachments/assets/30039e0a-8e2e-4f42-94df-6edb500e8131" />

df.fillna(method='ffill')

<img width="1056" height="845" alt="Screenshot 2025-09-12 213609" src="https://github.com/user-attachments/assets/3a862b2d-ffcd-4266-8f5b-b2314abecb36" />

df.fillna(method='bfill')

<img width="1039" height="845" alt="Screenshot 2025-09-12 213726" src="https://github.com/user-attachments/assets/a8743d87-b889-487a-b527-129b55c6a13f" />

df.fillna({'GENDER':'MALE','ADDRESS':'THANDALAM','TOTAL':'75'})

<img width="1194" height="840" alt="Screenshot 2025-09-12 213934" src="https://github.com/user-attachments/assets/79b4e4db-9e00-408c-9005-357e59af8aa1" />

df1=pd.read_csv("/content/iris.csv")
df1

<img width="644" height="492" alt="Screenshot 2025-09-12 214032" src="https://github.com/user-attachments/assets/4659aeec-0ae5-4575-a3ab-827ea40f91b5" />

df1.describe()

<img width="608" height="364" alt="Screenshot 2025-09-12 214117" src="https://github.com/user-attachments/assets/5bc0fbfa-dccf-4a1d-802d-9c2e552c1138" />

import seaborn as sns
sns.boxplot(x='sepal_width',data=df1)

<img width="862" height="581" alt="Screenshot 2025-09-12 214209" src="https://github.com/user-attachments/assets/a40da953-8083-439a-b0cc-595f09e3f809" />

Q1=df1.sepal_width.quantile(0.25)
Q3=df1.sepal_width.quantile(0.75)
IQR=Q3-Q1
print(IQR)

<img width="1577" height="40" alt="Screenshot 2025-09-12 214302" src="https://github.com/user-attachments/assets/f66f6c1d-87e6-45ff-9fb7-3ddd047dd585" />

rid=df1[((df1.sepal_width<(Q1-1.5*IQR))|(df1.sepal_width>(Q3+1.5*IQR)))]
rid['sepal_width']

<img width="924" height="246" alt="Screenshot 2025-09-12 214347" src="https://github.com/user-attachments/assets/0259b4ea-e370-4755-82dc-66d44cff6cca" />

rid=df1[~((df1.sepal_width<(Q1-1.5*IQR))|(df1.sepal_width>(Q3+1.5*IQR)))]
rid

<img width="1295" height="502" alt="Screenshot 2025-09-12 214442" src="https://github.com/user-attachments/assets/576f4aa8-f80c-4595-83a3-7268c96f39aa" />

sns.boxplot(x='sepal_width',data=rid)

<img width="1233" height="564" alt="Screenshot 2025-09-12 214539" src="https://github.com/user-attachments/assets/ce829b7a-7e7e-4193-abfa-ddac4aad617a" />

import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(df1['sepal_width']))
z

<img width="924" height="659" alt="Screenshot 2025-09-12 214626" src="https://github.com/user-attachments/assets/db0430e6-3349-4cfb-901d-3630c239bc9a" />

df2=df1[z<3] 
df2

<img width="679" height="502" alt="Screenshot 2025-09-12 214724" src="https://github.com/user-attachments/assets/f758f85b-4d63-4650-ac3d-8c806f1cf851" />

















# Result
          Thus,the program is executed and the output is verified successfully.
