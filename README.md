# NYC_Taxi_fare_prediction
The aim of this project is to predict the fare amount (inclusive of tolls) for a taxi ride in New York City given the pickup and dropoff locations.

Steps involved in this project are as follows:
1. Data Preprocessing
   * Removing Null values
   * Removing outliers in pickup and dropoff coordinates
2. Feature Extraction
   * Extracted different features based on on the attribute "pickup_datetime"
   * Time, month, weekday, date, month were extracted
   * As the time of the day acts as an important factor in determining the fare_amount based on the busy traffic schedules.
   * An more important feature is distance.
        1. Firstly we have calculated Manhattan Distance (i.e. Distance between longitudes and distance between latitudes)
        2. Later we also calculated the Euclidean Distance ( sqrt of sum of squares of distances between each coordinates)
        3. Lastly we have also calculated the Haversine Distance using th formula
        4. As there was very high correlation between these 3 distances we ended up removing Manhattan and Euclidean Distances, and proceeded with Haversine Distance.
3. Preprocessing of new features
   * As we have added new features, there  might outliers associated with the new features added
   * We have plotted the box plot for Haversine Distance and removed the outliers which were outside IQR
4. Model training
   * Various regression methods were used to train the model
   * First starting with Linear Regression with RMSE = 3.577
   * Followed by Polynomial Regression with best RMSE = 3.427 at p = 3
   * Followed by Ridge Regression with RMSE = 3.466
   * Lastly by using Lasso Regression with RMSE = 3.472   
     These RMSE values are when predicted upon validation set.


**CONCLUSION**:   
    We have tried implementing the models with the best of our knowledge.   
    There might me many more models to try and train upon and many more features may be extracteed for the better results and accuracy or optimal RMSE.   
    The RMSE value was less for Ridge Regression model.   
