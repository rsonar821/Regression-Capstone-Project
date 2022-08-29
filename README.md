<h1 align="center"> Bike Sharing Demand </h1>

<h2 align="center"> Regression Capstone Project </h2>

<p align="center"> 
  <img src="Images/bike.jpg" alt="bike.png">
</p>

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Introduction </h2>

Currently Rental bikes are introduced in many urban cities for the enhancement of mobility comfort. It is important to make the rental bike available and accessible to the public at the right time as it lessens the waiting time. Eventually, providing the city with a stable supply of rental bikes becomes a major concern. The crucial part is the prediction of bike count required at each hour for the stable supply of rental bikes. The main objective is to make a predictive model, which could help them in predicting the bike demands proactively. This will help them in stable supply of bike wherever needed.

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Features </h2>

The objective of this project is to predict the number of bikes required at the bike rental store at the particular hour of the day according to the supply needed.
The features included in the project are: 
* Date: Date on which bike was rented (Format: year-month-day)
* Rented Bike Count: Count of bikes rented at each hour
* Hour: Hour of the day
* Temperature: Temperature of the hour in Celsius
* Humidity: Humidity% of the hour
* Windspeed: Wind Speed of the hour in m/s
* Visibility: Visibility of the hour in units of 10m
* Dew Point Temperature: Dew Point Temperature of the hour in Celsius
* Solar Radiation: Solar Radiation of the hour in MJ/m2
* Rainfall: Rainfall of the hour in mm
* Snowfall: Snowfall of the hour in cm
* Seasons: 4 seasons (Winter, Spring, Summer and Autumn)
* Holiday: Whether the day is a Holiday or a Working Day
* Functional Day: Whether the day is functional for renting bikes or not.

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Data Preprocessing </h2>

* First of all checked the shape of the dataset where the bikes rented count was 0 and then checked the shape of the dataset where the bike renting store was not functional and found out that the shape of both the datasets is the same and it was quite obvious that 0 bikes would be rented in the hour where the store was not functional, so removed the rows from the dataset where 0 bikes were rented in the hour.
* Converted the ‘Date’ column to date-time datatype and extracted the year, month name and the day from it.

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Exploratory Data Analysis </h2>

Some of the data insights obtained through Exploratory Data Analysis are as:
* Least number of bikes were rented on Sunday, showing that people tend to rent bikes on office days or for work purposes.
* Maximum number of bikes were rented in the Summer season whereas the least number of bikes were rented in the winter season, showing that people enjoy riding bikes in the summer season compared to the cold winter season.
* More bikes were rented on working days as compared to holidays indicating people tend to rent bikes for work and office purposes rather than leisure purposes.
* As the humidity increases, the number of bikes getting rented decreases thus a negative correlation.
* As the temperature increases the number of bikes being rented also increases thus a positive correlation.
* Wind speed fails to establish a good correlation with the number of bikes rented.

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Data Preparation for Modelling </h2>

* Converted ‘Month’ and ‘Day’ columns to numerical values.
* Converted the columns ‘Season’, ‘Holiday’ and ‘Year’ to numerical values using the ‘get_dummies’ function.
* Dropped the columns ‘Date’, ‘Dew Point Temperature', ‘Wind Speed’ and ‘Functioning Day’.
* Created X and Y variables as independent and dependent variables respectively.
* Split the data into training and testing dataset with the ratio of 80:20 respectively.
* Using Standard Scaler scaled the data in a common data range for better and accurate predictions.

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Algorithms Used </h2>

Calculated the R2 Score of all the algorithms using cross validation with 10 kfolds and the results were as follows:
* Linear Regression: 0.64
* Ridge Regression: 0.64
* Decision Tree Regressor: 0.81
* Random Forest Regressor: 0.90
* Gradient Boosting Regressor: 0.87
* XGBoost Regressor: 0.87

![------------------------------------------------------------------------](https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png)

<h2 align="center"> Conclusion </h2>

* Performed Hyperparameter Tuning using Randomized Search CV on Random Forest Regressor.
* The Random Forest Regressor gave the best predictions out of all the other algorithms.
* The most important features for the model were found out to be 'Temperature' and 'Hour'.
* People prefer riding bikes in hot weather and in hot seasons.
* The bike renting business is being loved by the people and the business is prospering and growing by the time.
* Need of maximum bikes for renting can be seen at the morning time of 8am and the evening time of 6pm.
