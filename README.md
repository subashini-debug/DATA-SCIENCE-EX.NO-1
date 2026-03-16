#EX.NO:1
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
          
        ```
        import numpy as np
import pandas as pd
data=pd.read_csv("SAMPLEIDS.csv")
data

![alt text](490496992-546e28c3-2f08-4d37-bb4c-87a5714646a4.png)

data.head(4)

![alt text](490648254-c90a056e-60ae-4636-89ce-66ecddcf640d-1.png)

 data.tail(7)


 ![alt text](490648469-6d055069-c419-459d-b381-74157b0e9b6c.png)

data.isnull()

![alt text](490649209-eb89266c-9fb3-4919-9d6a-614905b31a99.png)

 data.notnull()


 ![alt text](490649715-df24b5a2-330f-4988-8266-45d36568245b.png)

data.isnull().sum()


![alt text](490652196-24ac5caf-1b1c-43b7-9b23-f0a1e3ccacc1.png)

data.isnull().any()


![alt text](490653090-9ea42ec5-2b8b-407e-b715-9ad5e4854577.png)

data.dropna(axis=1)


![alt text](490653446-8a7b1fdd-e2c7-4754-b1eb-13dbd79f7466.png)

data.dropna(axis=0)

![alt text](490653955-08ab1d1d-81dd-44d7-9cfe-d07a5a573899.png)


data.fillna(0)


![alt text](490654264-9acbea9d-594e-4a40-baa1-4f162518c372.png)


data.bfill()


![alt text](490654817-ca68518c-5218-4d2f-9c07-6a2b4f4ba696.png)


data.fillna({'REGNO':0, 'NAME':'PRAVEEN'})

![alt text](490655361-cc4a2c71-1b2e-4205-8025-55677e484257.png)


ir=pd.read_csv("iris.csv")
ir

![alt text](490655777-f86f927d-f6c6-44a2-a2c1-973606e14ecf.png)

ir.describe()


![alt text](490656032-253d6ea6-af65-4415-8945-faa09d51d08a.png)


import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)


![alt text](490656430-d3f4d523-53e7-4cc2-90a8-ed17873ee235.png)


q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)

![alt text](490656777-42906448-97f1-479d-9046-40c5c6eb2883.png)


rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']

![alt text](490657212-fee26582-0536-4a6e-93aa-70b517b678e4.png)


rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid

![alt text](490657843-c0c8a28d-ce20-4a7e-9499-7b8df74a03ef.png)


import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z

![alt text](490658650-3e24b43d-311a-4b0e-820b-5066fa073f86.png)

















# Result
          
Thus the programs are executed successfully