# Capestone-Project-Bike-sharing-demand-prediction

# Introduction
Bike rental companies often face the challenge of accurately predicting bike demand, which is crucial for optimizing inventory management and pricing strategies. In this project, my goal was to develop a regression supervised machine learning model that could forecast the demand for bikes within a specific time period.

Initially, I obtained a dataset from a bike sharing company containing valuable information such as the number of bikes rented, rental timestamps, and various weather and seasonality features. The dataset also included details on other factors that could potentially impact bike demand, such as holidays and functional/non-functional days.

To ensure the data was ready for modeling, I conducted thorough preprocessing and cleaning. This involved handling missing values, transforming variables as necessary, and encoding categorical features. Once the data was prepared, I split it into training and test sets, reserving the latter for evaluating the model's performance.

Next, I experimented with different model architectures and hyperparameter settings to find the best performing model. I trained each model using the training dataset and assessed their performance on the test data. By comparing various metrics such as mean absolute error, root mean squared error, and R-squared, I identified the model that exhibited superior predictive accuracy.

Additionally, I conducted ablation studies to gain insights into the individual impact of features on the model's performance. By selectively removing or modifying certain features, I assessed their significance in predicting bike demand. Notably, I discovered that temperature, weather conditions, and seasonality features played pivotal roles in accurate demand forecasting.

Following model selection and evaluation, I deployed the chosen model in a live production environment. This allowed the bike sharing company to receive real-time predictions of bike demand, empowering them to make well-informed decisions regarding inventory management and pricing strategies. To ensure the model's continued effectiveness, I actively monitored its performance over time, promptly addressing any issues that might arise.

In summary, by developing and deploying a regression supervised machine learning model for bike demand prediction, I enabled the bike sharing company to optimize their operations. The model's high accuracy, as evidenced by an impressive R-squared value of 0.9 and  validated its effectiveness in accurately forecasting bike demand. The insights gained from ablation studies further enhanced our understanding of the influential factors driving demand. Ultimately, this project provided the company with a valuable tool for improving their inventory management and pricing decisions.

# Problem Statement

The objective of this project is to tackle the challenge of accurately predicting bike demand within a specific time frame for a bike rental company. Precise demand forecasting holds great significance for bike rental companies as it enables them to optimize their inventory and pricing strategies to meet customer needs effectively. However, bike demand prediction is a complex task due to the influence of diverse factors, including rental timestamps, weather conditions, and local events. Developing a machine learning model capable of accurately predicting bike demand empowers rental companies to make well-informed decisions regarding resource allocation and customer service.

My primary aim was to create a highly accurate machine learning model that minimizes mean absolute error and maximizes the R-squared value. Additionally, the model should provide valuable insights into the key factors impacting bike demand. These insights would enable the bike rental company to make informed, data-driven decisions to optimize their operations effectively.

# Dataset Description

*   **Date** - Date(year-month-day)
*   **Rented_Bike_Count** - Count of bikes rented at each hour
*   **Hour** - Hour of the day(0-23)
*   **Temperature** - Temperature for the day
*   **Humidity** - Humidity Measure
*   **Windspeed** - Windspeed
*   **Visibility** - Visibility Measure
*   **Dew point temperature** - Dew Point Measure
*   **Solar radiation** - Solar Radiation Measure
*   **Rainfall** - Rainfall in mm
*   **Snowfall** - Snowfall in cm
*   **Seasons** - Season Name
*   **Holiday** - Whether Holiday or Not
*   **Functional Day** - Functional Day or Not


# Approach 

## ***1. Know Your Data***
### Check Unique Values for each variable.
#### Missing Values/Null Values
     Our data set didn’t have any null values to be treated.
 
# Univariate analysis

![Bike Project](https://github.com/Ujjwalrai7/Capestone-Project-Bike-sharing-demand-prediction/assets/125723652/2ab6f6da-d382-47ce-960c-9fef880b61f7)

![Bike project 2](https://github.com/Ujjwalrai7/Capestone-Project-Bike-sharing-demand-prediction/assets/125723652/583fe06a-5ac9-4a07-a818-f2b596094fa2)

In order to understand the distribution for each feature, I plotted distplot along with its mean and median. Distplot is shows both histogram and kde plot and is best suited for continous data.

# Insights Gained
 
Right/Positive Skewed Distribution: Mode < Median < Mean: Rented_Bike_Count, Wind_speed, Solar Radiation

No Skew: Mean = Median = Mode : Hour, Temperature, Humidity,Rainfall,Snowfall

Left/Negative Skewed Distribution: Mean < Median < Mode: visibility

# Bivariate Analysis

![Bike per hour](https://github.com/Ujjwalrai7/Capestone-Project-Bike-sharing-demand-prediction/assets/125723652/8931b0d2-7df1-4903-a87d-ac02b6d300ae)

# Insights Gained

Lineplot for hour and rented bike count shows that:
* Demand for bike is more during 8-10 in morning and 18-20 in night.
* Bike demand from midnight start decreasing till 4 in morning then gradually increase and comes at peak in night.

# Multivariate Analysis

![Multi](https://github.com/Ujjwalrai7/Capestone-Project-Bike-sharing-demand-prediction/assets/125723652/a50e8a59-b03d-4930-b623-6c96bde7f404)

# Insights Gained
It is important to maintain demand based on the time to generate stable profit.
Based on time period if unable to maintain demand, it will create a chance of new competition.


# Various ML Models implemented and their evaluation matrices Performance

![Matrices ](https://github.com/Ujjwalrai7/Capestone-Project-Bike-sharing-demand-prediction/assets/125723652/931a32ab-0c91-442b-b28c-39191b4bca1f)

Based on the results, I want to consider using the Xg_boost_cv i.e., XGBRegressor with hyperparameter tunned model as final model. This model has the highest R2 values on test sets, which indicates that it is doing a good job of explaining the variance in the target variable. It also has the lowest MAE and RMSE values on the test set, which means that it is making relatively small and accurate predictions.


# Conclusion
The main goal of the project was to stablize bike demand at every hour. Based on the objective, it was found that:

* XGBRegressor models with hyperparameter tuning and CV shows promising result with R2 score of 0.9, therefore it can be used to solve this problem.

* Bike rental count is high during working days than on weekend.

* Bike demand shows peek around 8-9 AM in the morning and 6 - 7pm in the evening.

* People prefer to rent bike more in summer than in winter.

* Bike demand is more on clear days than on snowy or rainy days.

* Temperature range from 22 to 25(°C) has more demand for bike.

* 'Hour', 'Temperature(°C)', 'Humidity', 'Wind_speed','Visibility ', 'Solar_Radiation', 'Rainfall', 'Snowfall', 'Seasons', 'day of week ' regulates bike demand.
