AIM:

    To perform multivariate analysis on the given data set.
    
EXPLANATION:

    Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning. The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis. 
    
ALGORITHM:

       Step 1: Read the given data.
       Step 2: Get information from the data.
       Step 3: Perform the Multivariate Analysis.
       Step 4: Save the final data set into the file.
       
CODE:

import pandas as pd

import numpy as np

import seaborn as sbn

import matplotlib.pyplot as plt

df = pd.read_csv("/content/SuperStore.csv")

df.head(10)

df.info()

df.describe()

df.isnull().sum()

df['State'] = df["State"].fillna(df['State'].mode()[0])

df.isnull().sum()

df.dtypes

sbn.scatterplot(x=df['State'],y=df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(8,4))

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(8,4))

sbn.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("Postal Code")

plt.show()

states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("SALES")

plt.show()

sbn.barplot(x=df['Postal Code'],y=df['Ship Mode'],hue=df['Region'])
 
df.corr()

sbn.heatmap(df.corr(),annot=True)

 
OUTPUT:

![image](https://user-images.githubusercontent.com/123535064/230726433-99a683e9-8614-4fdd-b249-7424da21d82c.png)

![image](https://user-images.githubusercontent.com/123535064/230726437-b3825f94-738b-47d1-a7fd-1cc063e3b8f8.png)

![image](https://user-images.githubusercontent.com/123535064/230726440-c5499a2e-f87c-4be7-9594-2e91f5fa5cec.png)

![image](https://user-images.githubusercontent.com/123535064/230726447-c36e4d45-5904-481b-911f-7957f48a7e0c.png)

![image](https://user-images.githubusercontent.com/123535064/230726451-f616ee82-e6df-49c8-a346-e89d2299f281.png)

![image](https://user-images.githubusercontent.com/123535064/230726456-270203ef-10ed-4509-92de-2d270d477029.png)

![image](https://user-images.githubusercontent.com/123535064/230726463-c66e9d64-4ac9-4dbf-adf7-073a78c7792e.png)

![image](https://user-images.githubusercontent.com/123535064/230726470-19ec15c4-05d5-4d28-a9b7-f4bd60a5c9d5.png)

![image](https://user-images.githubusercontent.com/123535064/230726484-274b951d-94c7-4ef7-a2be-f14b6f36b908.png)

![image](https://user-images.githubusercontent.com/123535064/230726495-7c5a3c2c-d64b-48a9-ac60-514367cb8f78.png)

![image](https://user-images.githubusercontent.com/123535064/230726505-c8532f0f-b825-4788-a770-ae8af8e73ed8.png)

![image](https://user-images.githubusercontent.com/123535064/230726508-0ad29fd6-56d2-4261-a2c3-f4095d5b49d0.png)

![image](https://user-images.githubusercontent.com/123535064/230726514-537b316c-76fc-43d4-a7d1-fe8cbfdf81e1.png)



RESULT:

      Thus, the program to perform Multivariate Analysis on the given data set is successfully executed.


