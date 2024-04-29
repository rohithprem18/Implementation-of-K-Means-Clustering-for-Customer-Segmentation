# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
#### step 1. Start the program
#### step 2. Import pandas and matplotlib.pyplot
#### step 3. Read the dataset and transform it
#### step 4. Import KMeans and fit the data in the model
#### step 5. Plot the Cluster graph
#### step 6. End the program


## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ROHITH PREM S
RegisterNumber: 212223040172
```

```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
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


*/
```

## Output:
### data.head() function
![1](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/c715f2c5-c154-4f64-a605-d45f26136ec2)

### data.info()
![2](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/2fd320f1-c0b2-4ad9-bfbd-ffe50ff15923)

### data.isnull().sum() function
![3](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/9af09537-0666-41b6-9823-9c4f43f8e51f)

### Elbow method Graph
![4](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/bbedff43-43d5-491f-a795-f313d6597284)

### KMeans clusters
![5](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/54c2a7fd-4c13-4601-a820-feeb6323a24e)

![6](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/1158d78d-78f2-4327-9461-eceae3bcba45)

### Customer segments Graph
![7](https://github.com/rohithprem18/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/146315115/72037b16-92ff-4ecc-acc7-71ca7fdbec6b)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
