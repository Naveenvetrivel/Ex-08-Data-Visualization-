# Ex-08-Data-Visualization-

## AIM
To Perform Data Visualization on a complex dataset and save the data to a file. 

# Explanation
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Clean the Data Set using Data Cleaning Process
### STEP 3
Apply Feature generation and selection techniques to all the features of the data set
### STEP 4
Apply data visualization techniques to identify the patterns of the data.


# CODE
~~~
import pandas as pd
import numpy as np
df=pd.read_csv("Superstore.csv")

df.head()

#Data Visualization using Seaborn

import seaborn as sns
from matplotlib import pyplot as plt

#1.Line plot

plt.figure(figsize=(8,5))
sns.lineplot(x="Segment",y="Region",data=df,marker='o')
plt.xticks(rotation = 90)
sns.lineplot(x='Ship Mode',y='Category', hue ="Segment",data=df)
sns.lineplot(x="Category",y="Sales",data=df,marker='o')

#2.Scatterplot

sns.scatterplot(x='Category',y='Sub-Category',data=df)
sns.scatterplot(x='Category', y='Sub-Category', hue ="Segment",data=df)
plt.figure(figsize=(10,7))
sns.scatterplot(x="Region",y="Sales",data=df)
plt.xticks(rotation = 90)

#3.Boxplot

sns.boxplot(x="Sub-Category",y="Discount",data=df)
sns.boxplot( x="Profit", y="Category",data=df)

#4.Barplot

sns.barplot(x="Sub-Category",y="Sales",data=df)
plt.xticks(rotation = 90)
sns.barplot(x="Category",y="Sales",data=df)
plt.xticks(rotation = 90)

#5.Pointplot

sns.pointplot(x=df["Quantity"],y=df["Discount"])

#6.Count plot

sns.countplot(x="Category",data=df)
sns.countplot(x="Sub-Category",data=df)

#7.Histogram

sns.histplot(data=df,x ='Ship Mode',hue='Sub-Category')

#8.KDE Plot

sns.kdeplot(x="Profit", data = df,hue='Category')

#Data Visualization Using MatPlotlib

#1.Plot

plt.plot(df['Category'], df['Sales'])
plt.show()

#2.Heatmap

df.corr()
plt.subplots(figsize=(12,7))
sns.heatmap(df.corr(),annot=True)

#3.Piechart

df1=df.groupby(by=["Ship Mode"]).sum()
labels=[]
for i in df1.index:
    labels.append(i)
colors=sns.color_palette("bright")
plt.pie(df1["Sales"],labels=labels,autopct="%0.0f%%")
plt.show()

df3=df.groupby(by=["Category"]).sum()
labels=[]
for i in df3.index:
    labels.append(i) 
plt.figure(figsize=(8,8))
colors = sns.color_palette('pastel')
plt.pie(df3["Profit"],colors = colors,labels=labels, autopct = '%0.0f%%')
plt.show()

#4.Histogram

plt.hist(df["Sub-Category"],facecolor="peru",edgecolor="blue",bins=10)
plt.show()

#5.Bargraph

plt.bar(df.index,df['Category'])
plt.show()

#6.Scatterplot

plt.scatter(df["Region"],df["Profit"], c ="blue")
plt.show()              

#7.Boxplot

plt.boxplot(x="Sales",data=df)
plt.show()
~~~

# OUPUT
![image](https://user-images.githubusercontent.com/94165322/171086228-7ae7644d-915b-480e-a434-56938158ef54.png)
# Data Visualization Using Seaborn:
![image](https://user-images.githubusercontent.com/94165322/171086382-8d8d160c-040e-4a19-8e8c-a9be1ac67bf8.png)
![image](https://user-images.githubusercontent.com/94165322/171086425-d3988282-0377-4da0-ac72-e85e52efc61e.png)
![image](https://user-images.githubusercontent.com/94165322/171086505-9eea605f-ab81-4521-ae29-d0e0abde46dc.png)
![image](https://user-images.githubusercontent.com/94165322/171086544-29f37607-b78e-49dd-bdff-bed034db9e64.png)
![image](https://user-images.githubusercontent.com/94165322/171086568-1e2849f8-27bf-4501-ad86-55aa7459360a.png)
![image](https://user-images.githubusercontent.com/94165322/171086958-bd9b0dcf-94f3-454d-82e9-c99e49bc1509.png)
![image](https://user-images.githubusercontent.com/94165322/171086595-4eb3d6e1-bb16-4213-a7d1-c1b8823e0f45.png)
![image](https://user-images.githubusercontent.com/94165322/171086633-b6804820-aaaa-4d9c-b911-67e842d3371a.png)
![image](https://user-images.githubusercontent.com/94165322/171086644-20cb2031-f846-4917-ab52-a4e8447ffc22.png)
# Data Visualization Using Matplotlib:
![image](https://user-images.githubusercontent.com/94165322/171086692-f9d04aa8-1605-4345-8164-c5b6db40fadf.png)
![image](https://user-images.githubusercontent.com/94165322/171086707-0c60b2de-8473-4543-b83c-be2bae814bf0.png)
![image](https://user-images.githubusercontent.com/94165322/171086716-876f3de0-f1ab-4452-8dd6-0d84bb5e6b7f.png)
![image](https://user-images.githubusercontent.com/94165322/171087314-f1373399-2b7f-4331-8716-8f3686a62ffc.png)
![image](https://user-images.githubusercontent.com/94165322/171087334-7b3da6a6-cf7e-49bf-81c1-19b483c35cba.png)
![image](https://user-images.githubusercontent.com/94165322/171087369-fe41eaa3-e3b1-4034-ab2d-bfbb86ac7d3d.png)
![image](https://user-images.githubusercontent.com/94165322/171087384-b3c3b376-5055-49c9-83b6-c94f47437b51.png)

# RESULT
Hence, Data Visualization is applied on the complex dataset using libraries like Seaborn and Matplotlib successfully and the data is saved to file.
