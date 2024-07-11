# What drives the price of a car?

__Jupyter Notebook with code, experimentation, further insights, and deployment strategies:__ click here.
__Reference credit: Insights and the project demonstrated during the office hour for this week.__

## Business Goal
This project aims to identify which factors about a used car drive its price higher or lower. We have received a 426K row dataset that needs to be cleaned up, prepared, and used for this analysis.

## Data
The dataset contains 17 baseline variables, four of which are numeric and the remaining categorical. The target is the “price” of the car sold. The distribution of the price variable after the removal of the outliers and duplicates is shown below. As can be seen, the dataset has a long tail.


## Modeling and performance
We employed regression modeling to predict the car's price. The models evaluated include linear regression, Ridge Regression, and Lasso Regression. Each model was trained and evaluated using a train/test split, followed by cross-validation and hyperparameter tuning using GridSearchCV to oprimize performance.

Among these, Linear Regression model demonstrated slightly better performance with a Root Mean Square Error (RMSE) of 7499.53 and and R-squared (R^2) value of 0.6275. This means that the model preductions are off by about $7500 from the actual price of the car. Additionally, approximately 62.75% of the variance in the price of the car is explained by the features in the model.


As can be seen from the plot above, the predicted and the actual values are within the RMSE range until about $40,000. After that the prediction error seems to be higher. 


## Conclusions
__Recommendations to the Car Dealership to increase the sale prices for cars under $75,000:__
1.	As expected, some manufacturers’ cars, such as Ferrari, Aston Martin, and Tesla, had higher prices. So, buy these cars.
2.	On the other end, cars made by Fiat were priced lower than most cars. So do not buy Fiat cars.
3.	If the car had an electric, hybrid, gas, or other drive, it lowered the price of the vehicle. So purchase diesel vehicles. 
4.	Trucks (Vehicle type) commanded a higher price than pickups and other types of vehicles. So purchase more trucks.

__Future improvements for the analysis and other comments:__
1.	Since a lot of the diesel trucks were priced at $74,999 they probably skewed the result. It would be good to run this analysis with more rows and higher valued cars included and see if this still holds true.
2.	Maybe using something like K-fold Target encoding of the “Model” field (15,251 unique values, after dropping all rows with NaNs in different columns) might have yielded a better prediction.
3.	Additionally replacing the missing a “mean” value such as “white” for paint_color where it was null would have also retained more information for the analysis, and probably a better prediction.
4.	The plot for the car prices between 1000 and 75000 shows a long tail. Another attempt should be made with the log of the prices to account for the long tail.
5.	Better to compare the profit made in each case instead of the sale price might have been better. I presume the dealership wants to maximize profit for each vehicle sold, and not the sale price alone.


