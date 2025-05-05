# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
### NAME: KEERTHANA V
### REG NO: 212223220045
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program 

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KEERTHANA V
RegisterNumber: 212223220045
```
```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.cluster import KMeans

df = pd.read_csv('Mall_Customers.csv')

print("Dataset Head:\n", df.head())
```

## Output:
![image](https://github.com/user-attachments/assets/f6b94c26-9db0-42b3-9ca3-73dd2d0551b2)

```
X = df.iloc[:, [3, 4]].values  
wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)

plt.figure(figsize=(8, 5))
plt.plot(range(1, 11), wcss, marker='o')
plt.title('The Elbow Method')
plt.xlabel('Number of clusters')
plt.ylabel('WCSS')
plt.grid(True)
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/bf8439e3-5d77-4b6d-980b-c31787a63e0c)

```
kmeans = KMeans(n_clusters=5, init='k-means++', random_state=42)
y_kmeans = kmeans.fit_predict(X)

plt.figure(figsize=(8, 6))
colors = ['red', 'blue', 'green', 'cyan', 'magenta']
for i in range(5):
    plt.scatter(X[y_kmeans == i, 0], X[y_kmeans == i, 1], s=100, c=colors[i], label=f'Cluster {i+1}')
plt.scatter(kmeans.cluster_centers_[:, 0], kmeans.cluster_centers_[:, 1],
            s=300, c='yellow', label='Centroids', edgecolor='black')
plt.title('Customer Segments')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.grid(True)
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/b720aa1b-6960-4613-84c2-6e7e154b7897)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
