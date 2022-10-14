# Predict Sales for Rossmann Store
## <p align="center" dir="auto">Regression Model - Predict Sales</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195868214-5fdce8c4-a5b4-495c-8c32-78dfcb95b9d2.png" width="700" />
</div>


# 1. Rossmann Store and Business Problem
This is a challenge problem from kaggle, witch simulates a real business problem. Rossmann is a drugstore franchise that operates in 7 European countries with more than 3000 stores.
The problem is that the CEO needs to define a budget to invest in store renovations, and for that he asked us to make a sales forecast for each of his stores for the next 6 weeks


# 2. Data Overview
Feature   | Definition
:--------- | :------
Id   | an Id that represents a (Store, Date) duple within the test set
Store | 	a unique Id for each store
Sales | the turnover for any given day (this is what you are predicting)
Customers | the number of customers on a given day
Open | an indicator for whether the store was open: 0 = closed, 1 = open
StateHoliday | indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
SchoolHoliday | indicates if the (Store, Date) was affected by the closure of public schools
StoreType | differentiates between 4 different store models: a, b, c, d
Assortment | describes an assortment level: a = basic, b = extra, c = extended
CompetitionDistance | distance in meters to the nearest competitor store
CompetitionOpenSince[Month/Year] | gives the approximate year and month of the time the nearest competitor was opened
Promo | indicates whether a store is running a promo on that day
Promo2 | Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
Promo2Since[Year/Week] | describes the year and calendar week when the store started participating in Promo2
PromoInterval  | describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store


# 3. Assumptions
+ The data contains historical data of 1115 stores;
+ The data available are between 2013-01-01 and 2015-07-31;
+ Null values of competition distance was replaced to 200.000 meters, assuming that there are no competitors
+ Days when the stores were closed, were not considered


# 4. Solution Plan
## 4.1 Steps for deliver a solution:
+ **Data Description**: Treatment of the original data like: fill NA's, change data types and descriptive statistical analyses;
+ **Feature Engineering**: Create new derived features from the original ones to make a better Machine Learning Model;
+ **Data Filtering**: Select lines and columns to drop from the data like days when the stores were closed;
+ **Exploration Data Analyses**: Analyses of the features distribution to take insights of how impactant each feature will be for our model;
+ **Data Preparation**: Reescale each feature to a commom range for the model to learn;
+ **Feature Selection**: Use an algorithm (Boruta) to select the best features for the model;
+ **Machine Learning Modelling**: Apply Machine Learning models and measure their perfomance based on error like MAE, MAPE and RMSE;
+ **Hyper Parameter Fine Tuning**: Choose randomly the bests parameters for our chosen model;
+ **Business Results**: A table to show the income of each store for the next 6 weeks.


# 5. Results
## <p align="center" dir="auto">Table - Income for the next 6 weeks</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195875699-48bb8a60-4204-40de-9d0b-a1e2cda675b4.png" width="700" />
</div>
<p align="center" dir="auto">Here we can see the worst and best scenario for each store and the errors</p>
<hr size="10">

## <p align="center" dir="auto">Table - Total income of all stores</p>
<div align="center">
<img src="https://user-images.githubusercontent.com/103151311/195876953-88c992d0-6c61-42e3-a8d0-75af6be2f595.png" width="700" />
</div>
<p align="center" dir="auto">Here are the worst and best scenario for all stores added</p>


# 6. Conclusion
The income of all stores and their erros will be useful for the CEO to define a budget to renovate any store.
+ Delivered a table with all margin of errors, so he can define the best scenario for him
+ Deploy in the Heroku Cloud and configurating Flask API request by a Telegram Bot. The user types /store_id and gets the sales prediction of this store for the next six weeks.


# 7. Next Steps
+ Raise the acuracy of the model by adding new features like "customers", making a new algorithm that predicts it;
+ Collect feedback from the users to improve the usability if necessary




