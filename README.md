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

 <img width="996" height="754" alt="image" src="https://github.com/user-attachments/assets/c6596ab3-a707-4965-8c25-7bb27cb62e4f" />

``` IQR(Inter Quartile Range) import pandas as pd ir=pd.read_csv("iris.csv") ir ```

<img width="635" height="484" alt="image" src="https://github.com/user-attachments/assets/211bc826-3fd2-4b00-ae82-4ba1af2d8abd" />

``` ir.describe() ```

<img width="550" height="339" alt="image" src="https://github.com/user-attachments/assets/65421881-8071-46be-a893-859dc6c89c61" />

``` ir.shape ``` 

<img width="130" height="51" alt="image" src="https://github.com/user-attachments/assets/40f9100f-963c-460c-9c16-e0d7097612d7" />

 ``` ir.info() ```
<img width="477" height="298" alt="image" src="https://github.com/user-attachments/assets/54c517ac-93ff-44fc-a015-c3e0490a2f1b" />

``` import seaborn as sns sns.boxplot(x='sepal_width',data=ir) ```

<img width="763" height="656" alt="image" src="https://github.com/user-attachments/assets/e37c2538-fb80-4383-ab6d-e33e7d632e5b" />

``` #q1=ir.sepal_width.quantile(0.25) q3=ir.sepal_width.quantile(0.75) iqr=q3-q1 print(iqr) ``` 

<img width="130" height="33" alt="image" src="https://github.com/user-attachments/assets/7ee666c3-3977-460a-b07c-9d4aa3244926" />

``` out=ir[((ir.sepal_width<(q1-1.5iqr))|(ir.sepal_width>(q3+1.5iqr)))] out['sepal_width'] ```

<img width="440" height="125" alt="image" src="https://github.com/user-attachments/assets/f42ef233-c2a5-4242-8807-623dc1fa87df" />

``` nor=ir[~((ir.sepal_width<(q1-1.5iqr))|(ir.sepal_width>(q3+1.5iqr)))] nor['sepal_width'] ```

<img width="587" height="311" alt="image" src="https://github.com/user-attachments/assets/13a98e7d-ec64-411c-aee6-afd40ab789e8" />

 ``` sns.boxplot(x='sepal_width',data=nor) ```

 <img width="816" height="666" alt="image" src="https://github.com/user-attachments/assets/2f593aad-4707-45bf-828c-acc339021fa6" />

``` Z-SCOREimport numpy as np import pandas as pd df=pd.read_csv("heights.csv") df ``` 

<img width="266" height="544" alt="image" src="https://github.com/user-attachments/assets/88dabba0-c0dd-4b00-82f0-69deabc0f22f" />

 ``` import scipy.stats as stats q1 = df['height'].quantile(0.25) q2 = df['height'].quantile(0.5) q3 = df['height'].quantile(0.75) iqr = q3-q1 iqr ``` 

 <img width="252" height="51" alt="image" src="https://github.com/user-attachments/assets/05a1aee9-5936-4512-a477-cec6b5b3b3d6" />

``` low = q1 - 1.5iqr print(low) high = q3 + 1.5iqr print(high) ```

<img width="203" height="463" alt="image" src="https://github.com/user-attachments/assets/a4a4cfb9-5d0e-443f-bebe-c10c584fafa5" />

``` df1 = df[((df['height'] >=low)& (df['height'] <=high))] df1 ``` 

<img width="215" height="51" alt="image" src="https://github.com/user-attachments/assets/82c739b2-be61-46d7-8312-3ef1df4f7d1e" />

``` z = np.abs(stats.zscore(df['height'])) z ``` 

<img width="411" height="367" alt="image" src="https://github.com/user-attachments/assets/a7b878ba-ab1a-4e28-8164-61750956394b" />

~~~
df1 = df[z<3] df1
~~~

<img width="282" height="505" alt="image" src="https://github.com/user-attachments/assets/bbfa6dba-59fe-478f-aa7d-7f65293a39f2" />

# Result

Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
