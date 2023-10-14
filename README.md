# ODD2023-Datascience-Ex-04
# AIM
To perform Multivariate EDA on the given data set.

# EXPLANATION
Exploratory data analysis is used to understand the messages within a dataset.
This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.
The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
# ALGORITHM
### STEP 1
Import the built libraries required to perform EDA and outlier removal.

### STEP 2
Read the given csv file

### STEP 3
Convert the file into a dataframe and get information of the data.

### STEP 4
Return the objects containing counts of unique values using (value_counts()).

### STEP 5
Plot the counts in the form of Histogram or Bar Graph.

### STEP 6
Use seaborn the bar graph comparison of data can be viewed.

### STEP 7
Find the pairwise correlation of all columns in the dataframe.corr()

### STEP 8
Save the final data set into the file
# CODE:
Name : A.ASHWIN KUMAR
register number : 212222100006
## diabetes.csv
```
import pandas as pd
import numpy as np
from scipy import stats
import seaborn as sns
import matplotlib.pyplot as plt

data=pd.read_csv("/content/diabetes (1).csv")
df=pd.DataFrame(data)

df
df.info()
sns.boxplot(data=df)
sns.scatterplot(data=df)

z = np.abs(stats.zscore(df['Glucose']))
dfc=df[(z<2)]
z = np.abs(stats.zscore(dfc['BloodPressure']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['SkinThickness']))
dfc=dfc[(z<3)]
z = np.abs(stats.zscore(dfc['BMI']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Insulin']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['DiabetesPedigreeFunction']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Age']))
dfc=dfc[(z<2)]
z = np.abs(stats.zscore(dfc['Outcome']))
dfc=dfc[(z<3)]

sns.barplot(x=df["Outcome"],y=df["Glucose"],data=df)
sns.scatterplot(x=df["Glucose"],y=df["BloodPressure"],data=df)

plt.figure(figsize=(17,7))
sns.scatterplot(x=df["Glucose"],y=df["BloodPressure"],hue=df['Outcome'])

glucose_new = df.loc[:, ["Glucose", "Outcome"]]
glucose_new = glucose_new.groupby(by=["Glucose"]).sum().sort_values(by="Outcome")
plt.figure(figsize=(17,7))
sns.barplot(x=glucose_new.index,y="Outcome",data=glucose_new)
plt.xticks(rotation = 90)
plt.xlabel=("Glucose")
plt.ylabel=("Outcome")
plt.show()

g_new=df.loc[:,["Age","BMI"]]
g_new=g_new.groupby(by=["Age"]).sum().sort_values(by="BMI")
#plt.figure(figsize=(10,7))
sns.barplot(x=g_new.index,y="BMI",data=g_new)
plt.xticks(rotation = 90)
plt.xlabel=("Age")
plt.ylabel=("BMI")
plt.show()

sns.barplot(x=df["SkinThickness"],y=df["Age"],hue=df['Outcome'])

df.corr()
sns.heatmap(df.corr(),annot=True)
```
## OUTPUT:
### before cleaning:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/091d7e4b-095b-4c05-b47b-e1cb5d05fbfd)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/8dab499b-3d6e-40d5-b854-c733ad05a692)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/bcb9ab23-a1c1-4103-8567-05b51b0edf64)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/3d9eec1b-cd1e-4bbb-99b9-a7e8c72e0972)
### after cleaning:
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/e9782ea6-eecb-4ff5-a81e-562120647079)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/6f303fa4-b73e-4526-8e50-ed73bd492fd1)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/2c70cd2c-7b0c-4b20-aa52-a3e197835a38)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/0106a7eb-0587-4a39-8317-5fec38a099d1)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/41818563-c25b-435e-87c6-b06e5ceb7a14)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/9a1b9026-eec4-4c95-851d-88d1f842e08d)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/cb813c1f-c6e0-4b13-af9f-a86a5df2783c)
![image](https://github.com/ASHWINKUMAR2903/ODD2023-Datascience-Ex-04/assets/119407186/5e0058ed-daa4-46c0-bcad-3a8a2ee25a58)

### SuperStore.cvs
```

```
## OUTPUT:
