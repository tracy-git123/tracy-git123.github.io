---
layout: project
type: project
image: img/sendy-delivery-1024x669.png
title: "Predicting Delivery Arrival Time - Sendy"
date: 2020
published: true
labels:
  - Python
  - Sci-kit Learn
  - Predictive model
  - Machine Learning
  - Regression
  - Logistics
summary: "This was a predictive modelling project where a model was trained to predict the arrival time of a delivery."
---

This project made use of data from over 28 000 deliveries completed by Sendy in Nairobi, Kenya.
The dataset used to train the predictive model used 21 201 data points while the model was test on 7 068 data points.
The aim was was to optimise the model to improve the Mean Sqaured Error score.


Here is a summary of columns that are found in the dataset which represent the delivery attributes that can be used to predict delivery time:

```cpp
Data columns (total 25 columns):
 #   Column                                Non-Null Count  Dtype  
---  ------                                --------------  -----  
 0   Order_No                              7068 non-null   object 
 1   User_Id                               7068 non-null   object 
 2   Vehicle_Type                          7068 non-null   object 
 3   Platform_Type                         7068 non-null   int64  
 4   Personal_or_Business                  7068 non-null   object 
 5   Placement_-_Day_of_Month              7068 non-null   int64  
 6   Placement_-_Weekday_(Mo_=_1)          7068 non-null   int64  
 7   Placement_-_Time                      7068 non-null   object 
 8   Confirmation_-_Day_of_Month           7068 non-null   int64  
 9   Confirmation_-_Weekday_(Mo_=_1)       7068 non-null   int64  
 10  Confirmation_-_Time                   7068 non-null   object 
 11  Arrival_at_Pickup_-_Day_of_Month      7068 non-null   int64  
 12  Arrival_at_Pickup_-_Weekday_(Mo_=_1)  7068 non-null   int64  
 13  Arrival_at_Pickup_-_Time              7068 non-null   object 
 14  Pickup_-_Day_of_Month                 7068 non-null   int64  
 15  Pickup_-_Weekday_(Mo_=_1)             7068 non-null   int64  
 16  Pickup_-_Time                         7068 non-null   object 
 17  Distance_(KM)                         7068 non-null   int64  
 18  Temperature                           5631 non-null   float64
 19  Precipitation_in_millimeters          199 non-null    float64
 20  Pickup_Lat                            7068 non-null   float64
 21  Pickup_Long                           7068 non-null   float64
 22  Destination_Lat                       7068 non-null   float64
 23  Destination_Long                      7068 non-null   float64
 24  Rider_Id                              7068 non-null   object 
dtypes: float64(6), int64(10), object(9)
```

1) The attributes I chose to include in the model were: 
- Day of the week - since traffic conditions on the weekend or weekday influnce delivery times
- Precipitation - since rain will impact traffic congestion on the road system
- Distance - between the Sendy depot and the delivery destination

```cpp
train1 = train1[['Pickup_-_Weekday_(Mo_=_1)',
'Precipitation_in_millimeters','Distance_(KM)','Time_from_Pickup_to_Arrival' ]]

test1 = test1[['Pickup_-_Weekday_(Mo_=_1)',
'Precipitation_in_millimeters','Distance_(KM)']]
```

I streamlined the string values into numerical values in both the train and test data sets:

```cpp
#weekdays get a dummy value of 0
train1['Pickup_-_Weekday_(Mo_=_1)'] = train1['Pickup_-_Weekday_(Mo_=_1)'].replace([1,2,3,4,5],0)

#weekend days get a dummy value of 1
train1['Pickup_-_Weekday_(Mo_=_1)'] = train1['Pickup_-_Weekday_(Mo_=_1)'].replace([6,7],1)

#no rain day get dummy 0
train1['Precipitation_in_millimeters'] = train1['Precipitation_in_millimeters'].fillna(int(0))

#rain days get dummy 1
train1.loc[train1['Precipitation_in_millimeters'] >0] = int(1)
```

I then created a column to store the predicted delivery times in the test-dataframe:

```cpp
test1['Time_from_Pickup_to_Arrival'] = np.nan
test1['Time_from_Pickup_to_Arrival'].unique()
test1.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 7068 entries, 0 to 7067
Data columns (total 4 columns):
 #   Column                        Non-Null Count  Dtype  
---  ------                        --------------  -----  
 0   Pickup_-_Weekday_(Mo_=_1)     7068 non-null   int64  
 1   Precipitation_in_millimeters  7068 non-null   float64
 2   Distance_(KM)                 7068 non-null   int64  
 3   Time_from_Pickup_to_Arrival   0 non-null      float64
dtypes: float64(2), int64(2)
memory usage: 221.0 KB
```

2) Model training using the the training dataset:

```cpp
x = train1.drop('Time_from_Pickup_to_Arrival', axis=1)
y = train1['Time_from_Pickup_to_Arrival']
>>> n_samples, n_features = 10, 5
>>> rng = np.random.RandomState(0)
>>> y = train1['Time_from_Pickup_to_Arrival']
>>> X = train1.drop('Time_from_Pickup_to_Arrival', axis=1)

reg = make_pipeline(StandardScaler(), SGDRegressor(max_iter=1000, tol=1e-3))

reg.fit(X, y)

y_preds = reg.predict(X)
```

3) Next I calculated the root mean squared error between the between the predicted delivery time and the actual delivery times:

```cpp
def rmse(y_test, y_predict):
  return np.sqrt(mean_squared_error(y_test, y_predict))
  
  answer = rmse(y, y_preds)
  answer
      794.4000853649443
```

4) Finally I applied the model to predict delivery times on the test dataset:

```cpp
xt = test1.drop('Time_from_Pickup_to_Arrival', axis=1)

ytest_preds = reg.predict(xt)
       
daf = pd.DataFrame(ytest_preds, columns=['Time_from_Pickup_to_Arrival'])
daf.head()
  Time_from_Pickup_to_Arrival
0 	1418.709746
1 	1124.555383
2 	1124.555383
3 	1124.555383
4 	1222.606838
```

Further tuning to the model and regression can be applied to lower the RMSE.
