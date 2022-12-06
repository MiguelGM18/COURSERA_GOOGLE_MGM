### Hola a todos, les dejo la liga a mi dashboard para aprobar el Curso de análisis de datos de Google en Coursea.

[DASHBOARD_MGM](https://app.powerbi.com/view?r=eyJrIjoiNzEzMWE0MDUtZGI2MC00ODc3LWJhZmUtNTE0ODY1MGZjZjU5IiwidCI6IjYwZTAwN2ViLTU1ZTUtNGIxZC1iMzU2LTkxNjJhN2M4ZDk4MCJ9&pageName=ReportSection56868b46218cc51c1e7d)

## También les comparto el script de Python para trabajar las bases de: Cyclistic a través de su cuenta de Google Drive

```
# Pandas is a software library written for the Python programming language for data manipulation and analysis.
import pandas as pd
# NumPy is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays
import numpy as np
# Matplotlib is a plotting library for python and pyplot gives us a MatLab like plotting framework. We will use this in our plotter function to plot data.
import matplotlib.pyplot as plt
#Seaborn is a Python data visualization library based on matplotlib. It provides a high-level interface for drawing attractive and informative statistical graphics
import seaborn as sns
# Preprocessing allows us to standarsize our data
from sklearn import preprocessing
# Allows us to split our data into training and testing data
from sklearn.model_selection import train_test_split
# Allows us to test parameters of classification algorithms and find the best one
from sklearn.model_selection import GridSearchCV
# Logistic Regression classification algorithm
from sklearn.linear_model import LogisticRegression
# Support Vector Machine classification algorithm
from sklearn.svm import SVC
# Decision Tree classification algorithm
from sklearn.tree import DecisionTreeClassifier
# K Nearest Neighbors classification algorithm
from sklearn.neighbors import KNeighborsClassifier
from posixpath import join
```

```
# Traer todos los datos de Google Drive en archivo csv para juntarlos
data1 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202209-divvy-publictripdata.csv")
data2 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202208-divvy-tripdata.csv")
data3 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202207-divvy-tripdata.csv")
data4 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202206-divvy-tripdata.csv")
data5 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202205-divvy-tripdata.csv")
data6 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202204-divvy-tripdata.csv")
data7 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202203-divvy-tripdata.csv")
data8 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202202-divvy-tripdata.csv")
data9 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202201-divvy-tripdata.csv")
data10 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202112-divvy-tripdata.csv")
data11 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202111-divvy-tripdata.csv")
data12 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202110-divvy-tripdata.csv")
data13 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202109-divvy-tripdata.csv")
data14 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202108-divvy-tripdata.csv")
data15 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202107-divvy-tripdata.csv")
data16 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202106-divvy-tripdata.csv")
data17 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202105-divvy-tripdata.csv")
data18 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202104-divvy-tripdata.csv")
data19 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202103-divvy-tripdata.csv")
data20 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202102-divvy-tripdata.csv")
data21 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202101-divvy-tripdata.csv")
data22 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202012-divvy-tripdata.csv")
data23 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202011-divvy-tripdata.csv")
data24 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202010-divvy-tripdata.csv")
data25 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202009-divvy-tripdata.csv")
data26 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202008-divvy-tripdata.csv")
data27 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202007-divvy-tripdata.csv")
data28 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202006-divvy-tripdata.csv")
data29 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202005-divvy-tripdata.csv")
data30 = pd.read_csv("/content/drive/MyDrive/Trabajo Final/202004-divvy-tripdata.csv")


values1 = data1[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values2 = data2[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values3 = data3[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values4 = data4[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values5 = data5[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values6 = data6[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values7 = data7[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values8 = data8[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values9 = data9[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values10 = data10[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values11 = data11[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values12 = data12[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values13 = data13[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values14 = data14[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values15 = data15[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values16 = data16[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values17 = data17[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values18 = data18[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values19 = data19[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values20 = data20[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values21 = data21[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values22 = data22[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values23 = data23[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values24 = data24[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values25 = data25[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values26 = data26[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values27 = data27[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values28 = data28[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values29 = data29[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]
values30 = data30[["ride_id","rideable_type","started_at","ended_at","start_station_name","start_station_id","end_station_name","end_station_id","start_lat","start_lng","end_lat","end_lng","member_casual"]]



dataframes = [values1,values2,values3,values4,values5,values6,values7,values8,values9,values10,values11,values12,values13,values14,values15,values16,values17,values18,values19,values20,values21,values22,values23,values24,values25,values26,values27,values28,values29,values30]
join = pd.concat(dataframes)

join.to_csv("CourseraMGM.csv")
```

```
## Crear de DF y ver que la información esté completa
dataacumulada = pd.read_csv("/content/CourseraMGM.csv")
print(dataacumulada)
```

```
## Descargar infirmación
from google.colab import files
files.download("CourseraMGM1.csv")
```
