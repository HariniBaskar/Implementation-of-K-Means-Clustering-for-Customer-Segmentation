# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Harini.B
RegisterNumber: 212221230035 
*/
```

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

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
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

![out1](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/05db3b82-ebd7-4da7-a8a8-5e2e7f5728fe)

![out2](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/5e6a4403-95cf-4bca-88f9-c485a96d81a7)

![out3](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/56bc26b2-26a3-48c7-b862-e5c5264bac35)

![out4](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/a7f0fe70-7dae-42ed-b56f-a3cf75ce1b6a)

![out5](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/5abc2c7e-f3d0-4866-9ecd-eee4fa6e3a32)

![out6](https://github.com/HariniBaskar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/93427253/161a86db-6564-4d09-8a26-3c343668f589)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
