# Implementation of K-Means Clustering Algorithm
## Aim
To write a python program to implement K-Means Clustering Algorithm.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation

## Algorithm:
Step1:
Import pandas and matplotlib.pyplot

Step2:
Import KMeans from sklearn package

Step3:
Read the csv fileusing df.head() and assign it to the variables

Step4:
Find the centroid using KMeans

Step5:
Run the program and predict the output

## Program:
```
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import seaborn as sns
import warnings
warnings.filterwarnings('ignore')

data=pd.read_csv('clustering.csv')
print(data.head(2))

x1=data.loc[:,['ApplicantIncome','LoanAmount']]
print(x1.head(2))

X=x1.values
sns.scatterplot(X[:,0],X[:,1])
plt.xlabel('Income')
plt.ylabel('Loan')
plt.show()

kmean=KMeans(n_clusters=4)
kmean.fit(X)

print('Cluster Centres:',kmean.cluster_centers_)
print('Labels:',kmean.labels_)

predicted_cluster=kmean.predict([[9200,110]])
print('the cluster group for the applicantincome 9200 and loan amount 110 is',predicted_cluster)
```
## Output:
![Screenshot from 2022-09-26 11-33-32](https://user-images.githubusercontent.com/113497680/192204365-b27ea223-2ea6-47d7-a18d-83f43bf1c10f.png)

## Result
Thus the K-means clustering algorithm is implemented and predicted the cluster class using python program.
