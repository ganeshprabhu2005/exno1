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








# Result
          <<include your Result here>>
