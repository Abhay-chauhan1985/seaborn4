# seaborn4
creating heat map using titanic data set
#importing libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline
#The data (let's start by reaching in the titanic_train.csv)
train=pd.read_csv('titanic_train.csv')
train.head()# data has been uploaded and we get first five rows of data.
PassengerId	Survived	Pclass	Name	                  Sex	Age	SibSp	Parch	Ticket	Fare	Cabin	Embarked
0	1	            0	      3	    Braund, Mr. Owen Harris	male	22.0	1	0	A/5 21171	7.2500	NaN	S
1	2	            1	      1	    Cumings, Mrs. John  	female	38.0	1	0	PC 17599	71.2833	C85	C
2	3	            1	      3	     Heikkinen, Miss. Laina	female	26.0	0	0	STON/O2. 3101282	7.9250	NaN	S
3	4	1	1	Futrelle, Mrs. Jacques Heath (Lily May Peel)	female	35.0	1	0	113803	53.1000	C123	S
4	5	0	3	Allen, Mr. William Henry	male	35.0	0	0	373450	8.0500	NaN	S

Exploratory data analysis: let's start some EDA,we'll start with checking out missing data
train.isnull()# it helps to find that particular value in row is null or not

#But the above method to check the null values is very cumborsome as it's not possible to check individual value here.so instead of this we can use seaborn to creat a simple heatmap to see where we are missing the data.

#creating heatmap
sns.heatmap(train.isnull(),yticklabels=False,cbar=False,cmap='viridis')

![image](https://user-images.githubusercontent.com/77687280/118932315-88081a80-b965-11eb-882d-764ad9f26542.png)

Roughly 20% of age data is missing.the proportion of age missing is likely small enough for reasonable replacement with some form of imputation. looking at cabin column,it looks like we are just missing too much.if that data to do something usefull with at a basic level.we will handle it later.
