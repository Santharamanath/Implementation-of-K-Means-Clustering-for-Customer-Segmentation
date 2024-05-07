# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by:Santha ramanath M 
RegisterNumber:212223220097  
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customers Segments")
```

## Output:
## Data set:

![324684886-e8603cec-123b-4d18-b875-90fc621b61ea](https://github.com/Santharamanath/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149035289/07f41458-08b0-4fda-bcb5-01279ab31016)


## Dataset information:


![324685005-3cffe4fb-91f4-43d1-b78f-0c869e19648d](https://github.com/Santharamanath/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149035289/2c19d6c1-c079-4b99-9b98-e773d4650ba6)


## Elbow method:

![324685139-7ce56d51-19b5-467d-9ca4-4d290967552d](https://github.com/Santharamanath/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149035289/40cf1f1d-e519-411f-a586-fce4298622dc)



## y_pred

![324685242-7fbac409-1c9a-49dd-b11e-e2e5e20f2687](https://github.com/Santharamanath/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149035289/5cd2385e-d60d-450e-8f8b-d7723a5dcd75)


## Cluster representing customer-segment graph

![324685399-6cf1f431-85f7-48fc-853a-069ca74190b2](https://github.com/Santharamanath/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/149035289/30e9eb47-fa41-4582-83d6-7bc08b09ab5c)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
