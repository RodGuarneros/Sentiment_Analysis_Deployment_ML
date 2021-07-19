# Sentiment Analysis Deployment Model
### By Rodrigo Guarneros

## Objective

<b>Here you can find a web application aimed to forecast if a movie review previously written is positive or negative</b>. This model was built with a particular module in Amazon Web Services: SageMaker using [XGBoost](https://xgboost.readthedocs.io/en/latest/) (A optimized distributed gradient boosting library designed to be highly efficient, flexible and portable), based on Python language.

## Procedure

This application connects the user with the Machine Learning Model throught an endpoint, having in mind a two-way flow of information: 
- The user types a movie review in the application
- The application sends this information to the model
- The model gathers and processes the information and generate a forecast
- The forecast (output) is given to the user

