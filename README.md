# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Start the program

2.Import pandas and matplotlib.pyplot.

3.Read the dataset and transform it.

4.Import KMeans and fit the data in the model.

5.Plot the Cluster graph.

6.End the program

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ROHITH PREM S
RegisterNumber: 212223040172
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square.
```
```
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
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
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### data.head() function
![EXP 8 DATA](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/bd60da6b-82e1-4eb1-86a5-ad79b695f0ff)
<br><br><br><br><br><br>
### data.info()
![exp 8 data info](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/70a0cb11-90f4-4d08-b8b7-ca4d0a61a0bc)

### data.isnull().sum() function
![exp 8 data isnull](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/ceaf252c-ff83-4c8a-8dfd-a64045de6858)
<br><br><br><br><br><br><br><br><br><br><br><br><br><br>

<br>

### Elbow method Graph
![exp 8 elbow graph](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/a9606d86-8c3f-436e-8f7e-bd53d1390758)

### KMeans clusters
![exp 8 kmesn 1](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/0cade90e-15eb-452a-a270-72c73dab6035)

![exp 8 kmean cluster](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/0df0da99-3abd-4cdf-80fb-1c4a0061cd09)

<br><br><br><br><br><br><br><br>
### Customer segments Graph
![exp 8 custom segment graph](https://github.com/23003250/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/139331462/9965fb26-21e7-4fb0-8be3-3d579c763b86)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
