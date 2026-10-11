# Online Retail Customer Analysis and Prediction

## Project Overview

This project performs an end-to-end analysis of an online retail dataset.

The project focuses on understanding customer purchasing behavior, identifying
important sales patterns, and building a machine learning model to classify
customers as regular or high-value customers.

The project covers:

- Data cleaning
- Exploratory Data Analysis (EDA)
- Customer feature engineering
- Data visualization
- Machine learning
- Model evaluation
- Customer classification
- Model saving

---

## Dataset

The project uses the **Online Retail Dataset** containing transactions from
an online retail store.

### Dataset Features

| Column | Description |
|---|---|
| InvoiceNo | Invoice/transaction number |
| StockCode | Product code |
| Description | Product description |
| Quantity | Number of products purchased |
| InvoiceDate | Date and time of transaction |
| UnitPrice | Price per unit |
| CustomerID | Unique customer identifier |
| Country | Customer's country |

A new feature called `TotalAmount` was created:

```text
TotalAmount = Quantity × UnitPrice
Project Objectives

The main objectives are:

1.Clean and preprocess the retail transaction data.
2.Analyze sales and customer purchasing patterns.
3.Identify top-performing products and countries.
4.Analyze customer purchasing behavior.
5.Create customer-level features.
6.Classify customers into regular and high-value customers.
7.Compare multiple machine learning algorithms.
8.Evaluate the trained models.
9.Save the final machine learning model for future use.

PROJECT STRUCTURE
OnlineRetailProject/
│
├── data/
│   ├── raw/
│   │   └── Online Retail.xlsx
│   └── processed/
│       ├── online_retail_cleaned.csv
│       └── customer_features.csv
│
├── notebooks/
│   ├── 01_data_cleaning.ipynb
│   ├── 02_eda.ipynb
│   └── 03_prediction_model.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── eda.py
│   └── model.py
│
├── visualizations/
│   ├── monthly_sales_trend.png
│   ├── top_countries_sales.png
│   ├── top_products_sales.png
│   ├── sales_by_day.png
│   ├── sales_by_hour.png
│   ├── top_customers.png
│   ├── top_customers_frequency.png
│   ├── quantity_vs_sales.png
│   ├── correlation_heatmap.png
│   ├── confusion_matrix.png
│   ├── model_comparison.png
│   ├── random_forest_feature_importance.png
│   └── roc_curve.png
│
├── models/
│   ├── retail_model.pkl
│   └── scaler.pkl
│
├── reports/
│   └── project_report.md
│
├── README.md
├── requirements.txt
└── .gitignore

Data Cleaning

The following preprocessing steps were performed:

Removed duplicate records.
Removed transactions with missing CustomerID.
Removed records with missing product descriptions.
Converted InvoiceDate to datetime format.
Converted CustomerID to integer format.
Removed transactions with non-positive quantities.
Removed transactions with non-positive unit prices.
Created the TotalAmount feature.

The cleaned dataset was saved as:

data/processed/online_retail_cleaned.csv
Exploratory Data Analysis

The analysis examined several aspects of the retail business.

Sales Analysis

The project analyzed:

Monthly sales trends
Sales by country
Sales by product
Sales by day of the week
Sales by hour
Customer Analysis

Customer purchasing behavior was analyzed using:

Total spending
Number of orders
Total items purchased
Average order value
Number of unique products
Number of countries associated with purchases
Visualizations

The project generated several visualizations, including:

Monthly sales trend
Top countries by sales
Top products by sales
Sales by weekday
Sales by hour
Top customers
Customer purchase frequency
Quantity vs sales
Correlation heatmap
Customer Feature Engineering

Customer-level features were created from transaction data.

The following features were used:

TotalOrders
TotalItems
AverageOrderValue
AverageUnitPrice
UniqueProducts
UniqueCountries

Customers were classified as high-value customers when their total spending
was at or above the 75th percentile of customer spending.

The resulting customer dataset was saved as:

data/processed/customer_features.csv
Machine Learning

Three classification algorithms were evaluated:

1. Logistic Regression

Used as a baseline classification model.

2. Decision Tree

A tree-based classification model was trained with a maximum depth of 5.

3. Random Forest

A Random Forest classifier with 100 trees and a maximum depth of 8 was trained.

Model Evaluation

The models were evaluated using:

Accuracy
Precision
Recall
F1 Score
ROC-AUC

A confusion matrix and ROC curve were also generated.

The model comparison visualization is available in:

visualizations/model_comparison.png
Feature Importance

Random Forest feature importance showed the following distribution:

Feature	         Importance
TotalItems	     0.479023
TotalOrders	     0.208248
UniqueProducts	     0.165115
AverageOrderValue	0.092030
AverageUnitPrice	0.055156
UniqueCountries	0.000428

TotalItems had the highest feature importance, followed by TotalOrders
and UniqueProducts.

Model Saving

The trained Random Forest model was saved using Joblib:

models/retail_model.pkl

The feature scaler was saved as:

models/scaler.pkl

These files allow the trained model to be reused without retraining it.

Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Joblib
Jupyter Notebook
OpenPyXL
Key Business Insights

The analysis can help a retail business understand:

Which countries generate the most sales.
Which products contribute significantly to revenue.
When customers are most active.
Which customers purchase frequently.
Which purchasing behaviors are associated with high-value customers.
Which customer characteristics are most useful for classification.

These insights can support customer segmentation and targeted marketing
strategies.

Future Improvements

Possible improvements include:

Customer segmentation using clustering.
RFM analysis (Recency, Frequency, Monetary).
Customer lifetime value prediction.
Time-series sales forecasting.
Hyperparameter tuning.
Cross-validation.
Deployment using Flask or Streamlit.
Real-time customer prediction.
A business dashboard for interactive analysis.
Conclusion

This project demonstrates a complete data science workflow using a real-world
retail transaction dataset.

The workflow progresses from raw data cleaning and exploratory analysis to
feature engineering, machine learning, model evaluation, and model
persistence.

The project provides both analytical insights into retail purchasing behavior
and a machine learning approach for identifying high-value customers.