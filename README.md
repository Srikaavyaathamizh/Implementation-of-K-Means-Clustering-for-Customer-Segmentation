# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1. 1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
```
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SRIKAAVYAA T
RegisterNumber:  212223230214
*/
```


## Program

```
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
```
## Output:
![Screenshot 2024-10-30 111350](https://github.com/user-attachments/assets/31163961-a3f4-4555-b21f-439cedfb47d9)

```
data.info()
```

## output
![Screenshot 2024-10-30 111455](https://github.com/user-attachments/assets/6cb9078d-0259-4fd2-ac7a-d8504d67064d)


```
data.isnull().sum()
```
## output
![Screenshot 2024-10-30 111534](https://github.com/user-attachments/assets/547e8dd6-dced-45d6-8f6c-3b4e82b93ff5)


```
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans (n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
## output
![Screenshot 2024-10-30 111659](https://github.com/user-attachments/assets/00531ad7-c9dc-43be-8b2e-b243c81ad9f9)


```
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
y_pred
```

## output
![Screenshot 2024-10-30 111808](https://github.com/user-attachments/assets/03dd1e4d-e431-44a0-bd2e-999fc829b648)


```
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

## output
![Screenshot 2024-10-30 111847](https://github.com/user-attachments/assets/b4b11159-939a-46c2-b0a5-ae1a16fb1509)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
