# Predicting Diabetes

## Overview
This repository contains resources and code for analyzing diabetes-related data. Below is a breakdown of the contents:

## Data
Within the repository, you will find a resources directory containing CSV datasets and an SQL database. The datasets include various attributes related to diabetes, such as demographic information, medical history, lifestyle factors, and health outcomes.
Models

There are three Jupyter Notebook files in this repository, each implementing a different machine learning model:
a. Logistic Regression Model: This notebook contains code for training and evaluating a logistic regression model on the diabetes dataset.
b. KNN Model: This notebook implements a K-Nearest Neighbors (KNN) model for classification tasks using the diabetes data.
c. Random Forest Model: The third notebook demonstrates the usage of a Random Forest classifier for predicting diabetes-related outcomes.


## Model Performance
Each model has been evaluated based on various metrics and performance indicators. The results of these evaluations are summarized below:

### Logistic Regression Model: 
In our analysis, we initially evaluated a classification model without scaling the data, which resulted in a precision of 0.53 and a recall of 0.15 for the positive class. After applying data scaling techniques, we observed no significant improvement in model performance. However, upon incorporating feature engineering, specifically by introducing new interaction terms derived from existing features, we achieved notable enhancements in the model's predictive capabilities. The inclusion of these engineered features led to a higher precision of 0.56 and a slight improvement in recall to 0.15 for the positive class. These results suggest that while scaling the data alone had minimal impact, feature engineering played a crucial role in refining the model's ability to accurately classify instances, particularly in identifying positive cases.

### KNN Model: 


### Random Forest Model: 


## Final Analysis
After thorough evaluation and comparison of the models, a final analysis has been conducted to determine the most effective approach for predicting diabetes-related outcomes. This analysis considers factors such as accuracy, precision, recall, and computational efficiency.
Conclusion
Based on the analysis, the Logistic Regression model demonstrates superior performance in predicting diabetes-related outcomes compared to the other models. 
