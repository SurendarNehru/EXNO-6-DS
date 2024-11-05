# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

# Aim:
  To Perform Data Visualization using seaborn python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
NAME : SURRENDAR N
REG NO : 212222040165
```
```
import seaborn as sns
import matplotlib.pyplot as plt
x=[1,2,3,4,5]
y=[3,6,2,7,1]
sns.lineplot(x=x,y=y)
```
![Screenshot 2024-11-05 155614](https://github.com/user-attachments/assets/bbf44c80-7cd3-4d8e-9370-181d1e73bac7)



```
df=sns.load_dataset("tips")
df
```
![Screenshot 2024-11-05 155637](https://github.com/user-attachments/assets/b2e80bc6-1748-479b-a950-652f998501e9)


```
sns.lineplot(x="total_bill",y="tip",data=df,hue="sex",linestyle='solid',legend="auto")
```
![Screenshot 2024-11-05 155655](https://github.com/user-attachments/assets/2d1e7d96-b485-4eed-a2a9-c3c281417f23)


```
x=[1,2,3,4,5]
y1=[3,5,2,6,1]
y2=[1,6,4,3,8]
y3=[5,2,7,1,4]
sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)
plt.title("Multi-line Plot")
plt.xlabel('X Label')
plt.ylabel('Y Label')
```
![Screenshot 2024-11-05 155710](https://github.com/user-attachments/assets/8a61f55b-006d-4c9a-8cea-7eee49ec6362)


```
import seaborn as sns
import matplotlib.pyplot as plt
tips=sns.load_dataset('tips')
avg_total_bill = tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()
plt.figure(figsize=(8, 6))
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill')
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip')
plt.xlabel('Day of the week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
![Screenshot 2024-11-05 155747](https://github.com/user-attachments/assets/3cfd7f83-556d-4b61-a6ab-607d0351e61e)


```
avg_total_bill = tips.groupby('time')['total_bill'].mean()
avg_tip = tips.groupby('time')['tip'].mean()
p1 = plt.bar(avg_total_bill.index, avg_total_bill, label='Total Bill', width=0.4)
p2 = plt.bar(avg_tip.index, avg_tip, bottom=avg_total_bill, label='Tip', width=0.4)

plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Time of Day')
plt.legend()
```

![Screenshot 2024-11-05 155804](https://github.com/user-attachments/assets/1acd520d-4442-463e-9e80-fa93f65a4503)

```
years=range (2000, 2012)
apples = [0.895, 0.91, 0.919, 0.926, 0.929, 0.931, 0.934, 0.936, 0.937, 0.9375, 0.9372, 0.939]
oranges = [0.962, 0.941, 0.930, 0.923, 0.918, 0.908, 0.907, 0.904, 0.901, 0.898, 0.9, 0.896, ]
plt.bar(years, apples)
plt.bar(years, oranges, bottom=apples)
```
![Screenshot 2024-11-05 155815](https://github.com/user-attachments/assets/3c2d2075-e3b2-495f-847f-972a61d986db)


```
import seaborn as sns
dt= sns.load_dataset('tips')
sns.barplot(x='day', y='total_bill', hue='sex', data=dt, palette='Set1')
plt.xlabel('Day of the week')
plt.ylabel('Total Bill')
plt.title('Total Bill by Day and Gender')
```
![Screenshot 2024-11-05 155828](https://github.com/user-attachments/assets/dad49cd8-6da8-4fca-b444-3e17871e52ee)

```
import seaborn as sns
tips = sns.load_dataset('tips')
sns.scatterplot(x= 'total_bill', y='tip', hue='sex',data=tips)
plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
![Screenshot 2024-11-05 155841](https://github.com/user-attachments/assets/e7e9ea6c-1cf6-4dec-b416-d00f1f9d71cc)


```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
np.random.seed(0)
marks = np.random.normal(loc=70, scale=10, size=100)
marks
```
![Screenshot 2024-11-05 155855](https://github.com/user-attachments/assets/29bb3f01-8821-49cb-8eeb-dc2af16179dc)


```
sns.violinplot(x="day", y="total_bill", hue="smoker", data=tips, linewidth=2, width=0.6,
palette="Set3", inner="quartile")
plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Plot of Total Bill by Day and Smoker Status")
```
![Screenshot 2024-11-05 155906](https://github.com/user-attachments/assets/13cdc6af-5d43-4751-ad32-09088a637eed)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x ='day', y ='tip', data = tip)
```
![Screenshot 2024-11-05 155917](https://github.com/user-attachments/assets/c09d700c-4845-4d99-b153-4a4803eb9dd1)

```
import seaborn as sns
sns.set(style = 'whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```
![Screenshot 2024-11-05 155927](https://github.com/user-attachments/assets/2dadbdec-5e00-44c7-ab03-975b4d421587)


```
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='Set2',alpha=0.8)
```
![Screenshot 2024-11-05 155938](https://github.com/user-attachments/assets/afea1fc4-d276-46e2-bef3-6c9f4bc4cfd7)

```
sns.histplot(data=marks, bins=10, kde=True, stat='count', cumulative=False, multiple='stack', element='bars', palette='Set1', shrink=0.7)
plt.xlabel('Marks')
plt.ylabel('Density')
plt.title('Histogram of students Marks')
```
![Screenshot 2024-11-05 160007](https://github.com/user-attachments/assets/30c7f2ae-1179-4d92-9e24-2d3647375a16)


# Result:
Thus, the Data Visualization using seaborn python library for the given data is implemented successfully
