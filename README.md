# Implementation-of-K-Means-Clustering-for-Customer-Segmentation>

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required :
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm :

1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program

## Program :
```
-------------------------------------------------------------------------
Program to implement the K Means Clustering for Customer Segmentation.
Developed by : DEVADARSHAN A S
RegisterNumber : 212222110007
-------------------------------------------------------------------------
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

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
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
  
```

## Output:

### data.head()

![image](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/a800dcc5-7e42-4405-9f8e-b5dc3bd3cec8)

### data.info()

![image](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/7e02bda4-50a9-46e3-98fa-be7d6b2c5ca4)

### data.isnull.sum()

![image](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/972c30da-24de-4498-b005-d34599b0255e)

### Elbow Method Graph:

![Screenshot 2024-05-07 163346](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/4e7dc8aa-ba03-4b84-89f3-aeb3261decf9)

### KMeans clusters:

![image](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/a385bcc0-72b4-4391-a8ca-3ee9785e8209)

### y_predicton:

![image](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/52f90bfb-7eb0-4c58-8048-f77bf09dc7ad)

### Customer Segments Graph:

![Screenshot 2024-05-07 163355](https://github.com/DEVADARSHAN2/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119432150/f2b2e3ff-a953-4040-9348-39b37b6b138a)


## Result :
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
