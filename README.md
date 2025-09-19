### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 18/09/2025
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
#### Program 1:
```
import pandas as pd
df = pd.read_csv(r"C:\Users\admin\OneDrive\Documents\clustervisitor.csv")
df

cluster = { 'Young': df['Age'] <= 30,'Middle-aged': (df['Age'] > 30) & (df['Age'] <= 50), 'Elderly': df['Age'] > 50 }
cluster

count=[]
for group, condition in cluster.items():  
    visitors_in_group = df[condition]
    count.append(len(visitors_in_group))
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
    print(count)

import matplotlib.pyplot as plt
plt.bar(cluster.keys(),count,data=df)
plt.xlabel('Age Group')
plt.ylabel('Number visitors')
plt.show()
```
#### Output:
<img width="1394" height="489" alt="image" src="https://github.com/user-attachments/assets/7c9f0572-8b52-4c26-8bf5-33c62657a2c0" />
<img width="1396" height="587" alt="image" src="https://github.com/user-attachments/assets/992c402b-8b49-47d4-843d-8de8778b924a" />
<img width="1094" height="687" alt="image" src="https://github.com/user-attachments/assets/329e2866-aa52-4dc4-b312-2b66e032b479" />

#### Program 2:
```
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

sc=StandardScaler()
scaledata=sc.fit_transform(df3)
scaledata

kmeans=KMeans(n_clusters=3,random_state=42)
df3['cluster']=kmeans.fit_predict(df3)
df3

plt.scatter(df3['Age'],df3['Salary'],c=df3['cluster'])
plt.xlabel('Age')
plt.ylabel('Salary')
plt.title('Clustered Data')
plt.show()
```
#### Output:
<img width="1119" height="431" alt="image" src="https://github.com/user-attachments/assets/c91f8b9a-2a32-48c6-9299-a1c1e5524357" />
<img width="1115" height="464" alt="image" src="https://github.com/user-attachments/assets/35878f58-4d7f-4f11-a3e8-b1ab78508c56" />
<img width="1100" height="739" alt="image" src="https://github.com/user-attachments/assets/73b8f087-e482-44bd-9c9f-a125f4a3e241" />
<img width="1123" height="565" alt="image" src="https://github.com/user-attachments/assets/f6bc0bd5-01fa-4785-86bf-347fb8cad7e6" />

### Result:
Thus , The implement of Cluster and Visitor Segmentation for Navigation patterns in Python executed Successfully.
