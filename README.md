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

5.Print the outputs and end the program
## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Suji.G
RegisterNumber: 212222230152
#import packages
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
### Data.head():
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/26298ccd-1eda-401f-82b5-ae5fdf5dc8d9)
### Data.info():
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/e5829c57-80b6-417c-a10f-417955b941e7)
### Null Values :
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/97d8e6ab-a491-40a4-9760-15874a79e8e6)
### Elbow Method Graph:
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/69882a6a-9618-472b-a2c3-561526b538ea)
### K-Means Cluster Formation :
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/4891af0d-32f3-45fd-9260-f44334504742)
### Predicted Value :
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/28d82f2f-9af8-43bd-9488-9b63427b33d5)
### Final Graph :
![image](https://github.com/sujigunasekar/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119559822/209281ed-f69d-49b7-9478-d39572845e45)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
