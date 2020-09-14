# Flight_fare_prediction_accuracy_92_percent
For a traveller it is important to know the fare value of a trip, and as prices of flight ticket varies abruptly and it becomes hectic for a user to check different websites, use different deals. A flight fare prediction model will help inform the travellers with the optimal time to buy their flight tickets and understand trends in the airline industry.
# Variables

Airline, Date_of_Journey, Source, Destination, Route, Dep_Time, Arrival_Time, Duration, Total_Stops, Additional_Info, Price
--------------------------------------------------------------------------------------------------------------------------
1. Dropped 1 row for missing values and checked for duplicates.
2. Checked for outliers in the price variable. Box plot
    q75, q25 = np.percentile(train.loc[:,i], [75 ,25])
    iqr = q75 - q25
    min = q25 - (iqr*1.5)
    max = q75 + (iqr*1.5)
3. Journey day, month and weekday extracted from datetime
4. Duration is in hours and mins, converting that to mins
5. Categorising departure and arrival time to morning, afternoon, evening, and night
6. Refining total stops and additional info columns
7. Dropped DOJ and route
8. Airline and Additional Info grouping of classes
9. Checking variable type and label encoding
10. Standardising duration variable
11. X, y, and array formation
12. 'learning_rate': [0.01,0.05,0.1],'max_depth': [3,5,7],'n_estimators': [500] – GBM and XGB hyperparameters
13. "n_estimators": [100,300,500], "max_features": ["auto", "sqrt", "log2"], "min_samples_split": [2,4,8], "bootstrap": [True,False]
•	If “auto”, then max_features=n_features.
•	If “sqrt”, then max_features=sqrt(n_features).
•	If “log2”, then max_features=log2(n_features).
Whether bootstrap samples are used when building trees. If False, the whole dataset is used to build each tree.
The minimum number of samples required to split an internal node.
14. Cross validation with accuracy with k=5.
