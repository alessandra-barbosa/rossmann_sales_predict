# Rossman Drug Store - A sales forecast 
The objective of this project is a sales forecast for the Rossmann drugstore using machine learning

![sales-prediction-social](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann6.png)
# Business Problem
Need to set a budget to renovate the store because
the current forecast was not consistent. Greater precision and accuracy in sales forecasts was needed.

# Business Assumptions
- Database: Kaggle
- The days when stores were closed were removed from the analysis.
- Only stores with sales values bigger than 0 were considered.
- For stores which did not have Competition Distance information, it was considered that the distance should be the longest distance observed in the data set.
# Attribute List
- Id - identify a record (Store, Date, sales)
- Store - a unique Id for each store
- Sales - store sales in that day (this is what you are predicting)
- Customers - the number of customers in that day
- Open - an indicator for whether the store was open: 0 = closed, 1 = open
- StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
- SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
- StoreType - differentiates between 4 different store models: a, b, c, d
- Assortment - describes an assortment level: a = basic, b = extra, c = extended
- CompetitionDistance - distance in meters to the nearest competitor store
- CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
- Promo - indicates whether a store is running a promo on that day
- Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
- Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
- PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store
# Solution Strategy
The method used for the project was CRISP-DM, apply as the steps below:

**Data Description:** The goal is to use statistical metrics to identify outliers in the business scope and also analyze basic statistical metrics such as: mean, median, maximum, minimum, range, skew, curtosis and standard deviation.

**Feature Engineering**: The goal of this step is to obtain new attributes based on the original variables, in order to better describe the phenomenon to be modeled.

**Data Filtering**: The goal of this step it to filter rows and delete columns that are not relevant for the model or are not part of the business scope.

**Exploratory Data Analysis**: The goal of this step is to explore the data to find insights and better understand the impact of variables on model learning.
- Bivariaty analysis
![sales-prediction-EDA](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann.png)
- Bivariaty analysis
![sales-prediction-EDA](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann1.png)
- Multivariaty analysis
![sales-prediction-EDA](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann3.png)


**Data Preparation**: The goal of this step is to prepare the data prepare data for application of the machine learning model.  

**Feature Selection**: The goal of this step is to select the better attributes to train the model. It was used Boruta Algorithm to make the selection.

**Machine Learning Modeling**: The goal of this step is to do the machine learning model training.

**Hyperparameter Fine Tunning**: The goal of this step is to choose the best values for each of the parameters of the model selected in the previous step.

**Convert model performance to business values**:  The goal of this step is to convert model performance to a business result.

**Deploy Model to Production**: The goal of this step is to publish the model in a cloud environment so that other people or services can use the results to improve the business decision. The cloud application platform choosed was Heroku.

**Telegram Bot**: The goal of this step is to create a bot on the telegram app, that make possible to consult the forecast at any time.

# Tested Machine Learning Models 
- Average Model
- Linear Regression Model
- Linear Regression Regularized Model (Lasso)
- Random Forest Regressor
- XGBoost Regressor

# Machine Learning Models Performance
![image](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann_tab1.png)


# Machine Learnig Performance after Hyperparemeter Fine Tuning

![image](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann_tab2.png)

Although the Random Forest Regressor Model presented better performance, this model usually requires a large amount of space on the server in deploy step, generating a significant cost increase for the company. Therefore, it was choosen the XGBoost Regressor Model, which after the hyperparameter fine tuning presented similar performance and requires less space on the server, generating a lower cost for the company.

# Model performance vs Business values

In addition to overall sales prediction, it was also calculated the sales prediction for the worst and the best scenario.

**Model with XGBoost Regression**

![image](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann_tab3.png)

# How to access the prediction
## Pre-requirement

- Sign up Telegram and create an account

# Telegram
- To acess the predictions on Telegram, click in the below:

[<img alt="Telegram" src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white"/>]( https://t.me/rossmann_ab_bot)

# How to get the prediction
- Send the store number (one each time) and get the sales prediction for the next six weeks.
- If the store number does not exist, it will get as an answer the message: "Store Not Available".

![image](https://github.com/alessandra-barbosa/rossmann_sales_predict/blob/master/Img/rossmann_bot.png)

# Conclusion

Considering the first CRISP-DS cycle, the final model presented a usefull performance, considering the MAPE (Mean Absolute Percentage Error) of 0.09. However, for some stores, higher MAPE values were observed, such as 0.24 and 0.56, but this is a point that could be improved in the next CRISP cycle.

# Technologies
- Jupyter notebook
- Python

# Deploy into production
- Back end: Heroku
- Front end web: Telegram


[<img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/>]( https://www.linkedin.com/in/alessandra-barbosa)
