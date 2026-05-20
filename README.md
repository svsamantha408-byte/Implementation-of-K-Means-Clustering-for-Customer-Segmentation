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
5. Print the outputs and end the program

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: S.V.Samanthashree
RegisterNumber:  212225040362
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Load dataset
data = pd.read_csv("Mall_Customers (1).csv")

# Display dataset information
print(data.head())
print(data.info())
print(data.isnull().sum())

# Finding WCSS using Elbow Method
wcss = []

for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++')
    kmeans.fit(data.iloc[:, 3:5])
    wcss.append(kmeans.inertia_)

# Plot Elbow Graph
plt.plot(range(1, 11), wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.show()

# Applying K-Means
km = KMeans(n_clusters=5)
km.fit(data.iloc[:, 3:5])

# Predict cluster values
y_pred = km.predict(data.iloc[:, 3:5])

# Add cluster column
data["cluster"] = y_pred

# Separate clusters
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

# Plot clusters
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"],
            c="black", label="Cluster 0")

plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"],
            c="cyan", label="Cluster 1")

plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"],
            c="yellow", label="Cluster 2")

plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"],
            c="blue", label="Cluster 3")

plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"],
            c="green", label="Cluster 4")

plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.title("Customer Segments")
plt.legend()
plt.show()
*/
```

## Output:
<img width="708" height="154" alt="Screenshot 2026-05-20 151554" src="https://github.com/user-attachments/assets/03f02185-f49d-465d-a4bb-761cb43ecc85" />
<img width="528" height="305" alt="Screenshot 2026-05-20 151607" src="https://github.com/user-attachments/assets/22d2e8c1-44d9-4539-ac4d-b5a518353955" />
<img width="305" height="160" alt="Screenshot 2026-05-20 151618" src="https://github.com/user-attachments/assets/a37673b6-2cc9-46f4-8571-6e0333fb8b0e" />
<img width="770" height="581" alt="Screenshot 2026-05-20 151659" src="https://github.com/user-attachments/assets/2471eef7-c4b1-4ee5-8715-eac5a6c8e3c4" />
<img width="735" height="585" alt="Screenshot 2026-05-20 151713" src="https://github.com/user-attachments/assets/922595e8-2f55-464a-a61f-ca4d09d426d6" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
