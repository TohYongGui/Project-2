
# README: Predicting House Prices with Linear Regression


## Problem Statement

We are a team of data scientist working for (Real Estate Success Inc) that is in the residential home flipping business. Our goal is to utilise the housing data collected from 2006 to 2010 to build a Linear Regression model that best predicts the potential sale price for properties located in Ames, Iowa. Once we are able to accurately predicting the housing prices, we can better identify houses that are undervalued and the features to focus on renovation/repair works.

## Executive Summary
This Ames Housing Data is provided to describe the properties in Ames, lowa that were sold between the years 2006-2010. First step, we will need to do a data cleaning, the missing values were fixed and data types were corrected. Once the data was cleaned, Exploratory Data Analysis (EDA) was performed to explore the relationship between Sale Price and each feature. For numeric features, heatmap and correlation coefficients were used to examine whether is there a linear relationship. For categorical data, bar plots were developed to show the average sale price across categories. During EDA for categorical features, look out for clusters in Sale Prices that emerged.

After the EDA, features were handled to reduce dimensionality of the data and to account for the clusters that emerged during the EDA. If a categorical variable was coded during feature engineering, it was removed from the data frame. Categorical variable was removed from the data frame if it was coded during feature engineering. Any categorical variables of interest were dummified. In order to prepare for modelling, the data was divided into training sets (80% of data) and testing sets (20% of data). (NOTE: Four models were created for this project, this includes Ridge Regression, Lasso Regression, and Linear Regression. For the regression models with regularization techniques, dummy variables were created for all categorical variables that were not been coded. For the last Linear Regression, dummy variables were hand-picked based on EDA and the Lasso Regression as different sets of dummy variables were included in the models.)

Four models were built during the modelling stage: a Linear Regression with 337 features, Ridge Regression with 337 features, Lasso Regression with 20 features, and Linear Regression with 47 features. All the features included in the last Linear Regression Model were essential based on EDA or the Lasso regression. The four models were compared based on R2 score. After comparison, the highest scoring model was being selected for further evaluation using RMSE and residuals plots. 

Conclusions and recommendations were made based on the best-performing model.




## Table of Contents
1. [Imports](#Imports)
2. [Read-in Data](#Read-in-Data)
3. [Data Cleaning](#Data-Cleaning)  
    - [Shape](#Check-Shape)  
    - [Cleaning Functions](#Cleaning-Functions)
    - [Missing Values](#Check-for-Null/Missing-Values)
    - [Data Types](#Check-for-Data-Types)
    - [Unsual Values](#Check-for-Unusual-Values)
    - [Clean Data](#Export-Clean-Data)  
4. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
    - [Graphing Functions](#Graphing-Functions)
    - [Correlations with Target](#Heatmap-and-Correlations-for-Target)
    - [Distributions](#Distributions-of-Variables)
    - [Categorical Variables and Target](#Visualizing-Relationships-between-Categorical-Features-and-Sales-Price)
5. [Feature Engineering](#Feature-Engineering)
    - [Combine Train + Test Data](#Combine-Train-+-Test-Datasets-to-Ensure-Equal-Features-in-Train/Test-Datasets)
    - [Functions](#Functions)
    - [Features](#Create-Features)
    - [Split Train and Test Data](#Divide-Data-Back-into-Preprocessed-Train-and-Test-Sets)
6. [Model Preparation](#Model-Preparation)
    - [Ridge and Lasso Regression](#Models-1-3:-Overfit-Linear-Regression,-Ridge,-and-Lasso-Regression)
    - [Linear Regression](#Model-3:-Linear-Regression-Using-Handpicked-Features-Identified-by-EDA-and-Lasso)
7. [Modeling](#Modeling)
    - [Overfit Linear Regression](#Model-1:-Linear-Regression-(As-Precursor-to-Ridge-and-Lasso))
    - [RidgeCV Regression](#Model-2:-RidgeCV-Regression)
    - [LassoCV Regression](#Model-3:-LassoCV-Regression)
    - [Linear Regression](#Model-4:-Linear-Regression-with-Features-Identified-in-EDA-and-Lasso)
8. [Model Selection](#Model-Selection)
9. [Model Evaluation](#Model-Evaluation)
10. [Conclusions and Recommendations](#Conclusions-and-Recommendations)
11. [References](#References) 



## Model Selection
As previously mentioned, four models were created for this project. 

Model Name | Train Score | Test Score
-|-|-
Linear Regression (Overfit)|94.6%|74.9%
Ridge|89.8%|81.9%
LASSO|84.6%|80.8%
Linear Regression (Features from EDA and LASSO)|87.5%|87.8%

## Conclusions and Recommendations

The Linear Regression model is able to explain approximately 87% of the variation in the target (Sale Price) for both the train and test sets. On top of that, it's able to predict the sale price within $23,625.19. The model is good at predicting the price that falls within the range of \\$80,000 to \\$230,000. However, it has a weakness at predicting extreme values.


## References
1. [Population of Ames Iowa](https://datausa.io/profile/geo/ames-ia/)
2. [Machine Learning in Real Estate](https://unionstreetmedia.com/the-rise-of-machine-learning-in-real-estate/#:~:text=Personalized%20Marketing%20Automation%20%E2%80%93%20machine%20learning,neighborhood%20and%20property%20is%20best)
3. [Ames Housing Data - Original Article](#http://jse.amstat.org/v19n3/decock.pdf)
4. [How To Interpret R-squared in Regression Analysis](https://statisticsbyjim.com/regression/interpret-r-squared-regression/)


