# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess the customer data (normalize or scale the features).
2.Choose the number of clusters (k) and initialize the KMeans model.
3.Fit the KMeans model to the customer data to perform clustering.
4.Predict the cluster labels for each customer in the dataset. 5.Analyze and visualize the resulting customer segments. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: CHANTHRU V
RegisterNumber: 24900997

import os
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
print(data.head())
print(data.info())
data.isnull().sum()
wcss = [] 
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", n_init=10, random_state=42)
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()
km = KMeans(n_clusters=5, init="k-means++", n_init=10, random_state=42)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:, 3:])
print(y_pred)
data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 1")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 2")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 3")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 4")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 5")
plt.legend()
plt.title("Customer Segments")
plt.show() 
*/
```

## Output:

![Screenshot 2024-12-13 100100](https://github.com/user-attachments/assets/6ebf8084-0cec-4504-9ee8-60312afa2709)
![Screenshot 2024-12-13 100113](https://github.com/user-attachments/assets/7896c391-0180-4d14-a704-e99c86c85f22)
![Screenshot 2024-12-13 100128](https://github.com/user-attachments/assets/c8542d31-65d8-476d-9af0-ef52b42d2a31)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
