# Sales Forecasting for One of the Largest Turkish Food and Beverage Companies
Monthly sales forecasting in units for all cities of Turkey and their districts.

## Project Purpose
The project purpose is developing a model for monthly sales volume forecasting which beats the current prediction methods of the company and baseline predictions. Also, it is targeted that model can be drilled down till distribution point level from cities and districts.

## Notebooks of the project
* Data Cleansing & Preprocessing (Data Preprocessing Notebooks are not published due to confidentiality issues)
* [Classes & Functions used in Exploratory Analysis](https://github.com/dorukcanga/Sales-Forecasting-for-Food-and-Beverage-Industry/blob/master/project_functions.py)
* [Exporatory Data Analysis & Model Training](https://github.com/dorukcanga/Sales-Forecasting-for-Food-and-Beverage-Industry/blob/master/Exploratory_Analysis_and_Model_Training.ipynb)

## Dataset
* Sales Transactions of all brands of the company from 2014 to June 2019
* Customer Master Data

## Important Features
### Transaction Data:
* CustomerId
* Sales Amount in units
* Gross & Net Sales Amount in Turkish Liras
* Unit Price
* Tax Rate during transaction

### Customer Master Data:
* Address, City, District
* Segment Information

### Additional Features:
* Monthly Average Price Information
* Total Number of Holidays in a Given Period
* Number of Foreign Tourists Coming from Selected Countries
* Total Number of Ramadan Days in a Given Period
* Total Number of Religious Days in a Given Period
* Temperature
* Discount Percentage
* Customer Confidence Index
* Total Number of Stores in Selected City or District

## Project Outline
* Data Cleansing of Transaction Data & Creating Monthly Sales Data
* Baseline Predictions
* Time Series & Exploratory Data Analysis
* Feature Selection Analysis
* Model Evaluation with Training Set for both city and its districts
* Final Test of the Selected Model on Test Set

### Baseline Predictions:
Baseline predictions are made with both 12 months shift and average of last 3 months methods for selected city and its all districts

### Time Series & Exploratory Data Analysis:
Following Analysis are made for both monthly consolidated sales of the city and its districts:
* Rolling Mean & Standard Deviation, Monthly Boxplot
* Seasonal Decompose
* ADFuller Test
* ACF & PACF Plots

### Feature Selection
* Granger Causality
* Lasso Feature Importance
* Random Forest Feature Importance
* XGBoost Feature Importance

### Model Evaluation
SARIMAX, Facebook's Prophet and XGBoost models are trained on training set. Both rolling window and walk forward validation methods are used during model training. All of these models are trained for consolidated sales data of the city and all districts seperately. Also, ensemble of these 3 models and LSTM are implemented but extracted from the code due to their performances

### Model Selection and Final Test
SARIMAX is selected as final model and final test is made on test dataset with same parameters and features decided on model evaluation.

## Results
Prediction error (Mean Absolute Percentage Error - MAPE) is reduced to ~6% from ~14% (Baseline Error) for city prediction.
Average of MAPEs of districts is reduced to ~14% from ~19% (Baseline Error).
