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
~~~
Name: PRAKASH V
REG:212225230211
~~~
~~~
import pandas as pd data=pd.read_csv("SAMPLEIDS.csv") data
~~~
<img width="1042" height="805" alt="Screenshot 2026-05-21 092456" src="https://github.com/user-attachments/assets/421faf25-7ca4-4bc0-b3db-fd8169c7a90c" />

``` data.head() ```
<img width="1037" height="254" alt="Screenshot 2026-05-21 092640" src="https://github.com/user-attachments/assets/6a184db5-8b14-44a3-b742-ed976c48bcf6" />

``` data.tail() ```
<img width="1025" height="236" alt="Screenshot 2026-05-21 092740" src="https://github.com/user-attachments/assets/a4db8cb9-1347-4b3f-8a7a-47758a5711eb" />

``` data.isnull() ```
<img width="881" height="804" alt="Screenshot 2026-05-21 093142" src="https://github.com/user-attachments/assets/9bea8185-09cc-4593-b3bb-4ba6d742b481" />

``` data.isnull().sum() ``` 
<img width="161" height="331" alt="Screenshot 2026-05-21 093240" src="https://github.com/user-attachments/assets/c8175e10-fecd-4b27-a675-e6158f34ac22" />

 ``` data.isnull().any() ``` 
 <img width="192" height="334" alt="Screenshot 2026-05-21 093413" src="https://github.com/user-attachments/assets/156522cd-8bec-4fe7-a0e3-5d81bc077aa7" />

 ``` data.dropna() ```
 <img width="988" height="484" alt="Screenshot 2026-05-21 093535" src="https://github.com/user-attachments/assets/74d52f62-fdf7-47fc-b6c7-f6942269ef9e" />

 ``` data.fillna(0) ```
 <img width="995" height="758" alt="Screenshot 2026-05-21 093640" src="https://github.com/user-attachments/assets/f14b8eea-4665-4511-9215-5718d2da7676" />

``` data.fillna(method='ffill') ```
<img width="996" height="780" alt="Screenshot 2026-05-21 093742" src="https://github.com/user-attachments/assets/b398a3dd-18ef-48e2-a685-127d8cae6b7f" />

``` data.fillna(method='bfill') ```
<img width="999" height="756" alt="image" src="https://github.com/user-attachments/assets/89660d19-31b1-430c-8ca7-96f003178857" />

 ``` data.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999}) ```


# Result
