# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SURIYA PRAKASH.S
RegisterNumber: 212223100055
```

```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("/content/Mall_Customers.csv")
data.head(5)


data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="brown",label="cluster4")
print("SURIYA PRAKASH.S [212223100055]")
```

## Output:

### 1.DATA.HEAD():
![image](https://github.com/user-attachments/assets/77a1a160-23b5-4e11-8e62-8d5d56d13f8f)



### 2.DATA.INF0():

![image](https://github.com/user-attachments/assets/5e779c3b-2993-4220-852e-ddcf5377a270)


### 3.DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/87c7f429-59b6-406f-b313-615576f90cc4)



### 4.PLOT USING ELBOW METHOD:

![image](https://github.com/user-attachments/assets/5b2b4ad2-28e5-431c-84b1-76dc55f377dd)


### 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/92c03af4-4c4a-4814-9632-54068aa9cef3)




### 6.Y_PRED ARRAY:

![image](https://github.com/user-attachments/assets/65980c15-b182-420e-9065-38921e8b9aa8)


### 7.CUSTOMER SEGMENT:

![image](https://github.com/user-attachments/assets/7603d98f-d717-49a9-96fc-b825f3674ab8)




## Result:

Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.








