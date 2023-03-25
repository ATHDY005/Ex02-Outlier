# Ex02-Outlier

# AIM

You are given bhp.csv which contains property prices in the city of banglore, India.

You need to examine price_per_sqft column and do following,

(1) Remove outliers using IQR

(2) After removing outliers in step 1, you get a new dataframe.

(3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get

exact same result

(4) for the data set height_weight.csv find the following

(i) Using IQR detect weight outliers and print them

(ii) Using IQR, detect height outliers and print them

# ALGORITHM

## STEP 1:

Read the given Data

## STEP 2:

Remove the Outliers using IQR

## STEP 3:

Use zscore of 3 to remove outliers and save the data to the file .

## STEP 4:

Read the next given Data

## STEP 5:

 Using IQR detect weight outliers and print them
 
## STEP 6: 
 
 Using IQR, detect height outliers and print them

## STEP 7:
 
Save the data to the file.
 
# (1) Remove outliers using IQR 

import pandas as pd

import numpy as np

from scipy import stats

df1=pd.read_csv('/content/bhp.csv')

df2=pd.read_csv('/content/height_weight.csv')

df1.head()

q1=df1.quantile(0.25)

# (2) After removing outliers in step 1, you get a new dataframe.

q1=df1.quantile(0.25)


# (3) use zscore of 3 to remove outliers. This is quite similar to IQR and you will get exact same result

from scipy import stats

z=np.abs(stats.zscore(df1['price_per_sqft']))

df1['price_per_sqft'][(z>3)]

print(df1)

df = pd.read_csv("height_weight.csv")

print(df)

# (4) for the data set height_weight.csv find the following

# (i) Using IQR detect weight outliers and print them
     
     
Q1 = df['weight'].quantile(0.25)

Q3 = df['weight'].quantile(0.75)

IQR = Q3-Q1

df3=df[((df['weight']<=Q1-1.5*IQR)|(df['weight']>=Q3+1.5*IQR))]

df3


# (ii) Using IQR, detect height outliers and print them
    
Q1 = df['height'].quantile(0.25)

Q3 = df['height'].quantile(0.75)

IQR = Q3-Q1

low=Q1-1.5*IQR

high=Q3+1.5*IQR

dff=df[((df['height']<=low)|(df['height']>=high))]

dff

# OUTPUT:

![image](https://user-images.githubusercontent.com/84709944/227706948-b3f591ef-86ce-4967-87be-7907651df48a.png)

![image](https://user-images.githubusercontent.com/84709944/227706990-eb9a7a84-c92f-4e0d-82f4-a411085c695f.png)

![image](https://user-images.githubusercontent.com/84709944/227707004-0d464fd1-c05f-4eb2-a064-88c63755b4a7.png)

![image](https://user-images.githubusercontent.com/84709944/227707012-4abae652-673e-44d6-aa2f-96c958644be2.png)

![image](https://user-images.githubusercontent.com/84709944/227707038-6ed968b1-7541-428b-91ba-a6c678c727d4.png)

![image](https://user-images.githubusercontent.com/84709944/227707058-6aa2374b-b2c7-43dd-bb8e-bf1daa9a4a08.png)

# RESULT:

Thus the outliers are removed and the given data are examined. 
