# Predicting Diabetes

## Overview
This repository contains resources and code for analyzing diabetes-related data. Below is a breakdown of the contents:

## Data
Within the repository, you will find a resources directory containing CSV datasets and an SQL database. The datasets include various attributes related to diabetes, such as demographic information, medical history, lifestyle factors, and health outcomes.
Models

There are six Jupyter Notebook files in this repository, each implementing a different machine learning model:
a. Logistic Regression Model: This notebook contains code for training and evaluating a logistic regression model on the primary diabetes dataset.
b. KNN Model: This notebook implements a K-Nearest Neighbors (KNN) model for classification tasks using the primary diabetes data.
c. Random Forest Model: The third notebook demonstrates the usage of a Random Forest classifier for predicting diabetes-related outcomes with the primary dataset.
d. EDA_main: This notebook contains the exploratory data analysis for the primary data set. 
e. EDA_secondary: This notebook contains exploratory data analysis for the secondary data set which contained features obtained in a medical setting
f. Random_Forest_secondary: This notebook contains the random forest model for the secondary dataset.



## Model Performance
Each model has been evaluated based on various metrics and performance indicators. The results of these evaluations are summarized below:

### Logistic Regression Model: 
In our analysis, we initially evaluated a classification model without scaling the data, which resulted in a precision of 0.53 and a recall of 0.15 for the positive class. After applying data scaling techniques, we observed no significant improvement in model performance. However, upon incorporating feature engineering, specifically by introducing new interaction terms derived from existing features, we achieved notable enhancements in the model's predictive capabilities. The inclusion of these engineered features led to a higher precision of 0.56 and a slight improvement in recall to 0.15 for the positive class. These results suggest that while scaling the data alone had minimal impact, feature engineering played a crucial role in refining the model's ability to accurately classify instances, particularly in identifying positive cases.

### KNN Model: 


### Random Forest Model: 

A random forest model was employed to attempt to predict if a survey respondent would be diagnosed with diabetes or not. The first iteration of the Random Forest model scaled all features and was run with 500 estimators. The model was attempted with fewer and greater estimators with declining results either way. 
Feature importance was determined with the ‘feature_importances_’ function, and indicated that ‘BMI,’ ‘Age,’ ‘Income,’ ‘PhysHlth,’ and ‘GenHlth,’ were the most important features in this model. 
A classification model was produced and had the following results: 
Precision 0 : 0.88, Recall 0 : 0.97
Precision 1 : 0.50, Recall 1 :  0.17
Accuracy: 0.86

These results indicate that while the model is good at predicting cases where the survey respondents didn’t have diabetes, it largely failed to categorize true diabetes cases as positive cases. 
The Random Forest Model was then modified to attempt to improve its ability to capture positive diabetes cases from survey responses. 

-Only continuous variables were scaled (‘BMI,’ ‘PhysHlth,’ ‘MentHlth’).
-Less important features were dropped.
-A number of new features were created.
-Categorical variables were converted to dummy variables.

None of these attempts at optimizing the model were successful in significantly increasing the model’s ability to capture true diabetes cases. 

## Final Analysis
After thorough evaluation and comparison of the models, a final analysis has been conducted to determine the most effective approach for predicting diabetes-related outcomes. This analysis considers factors such as accuracy, precision, recall, and computational efficiency.
Conclusion
Based on the analysis, the Logistic Regression model demonstrates superior performance in predicting diabetes-related outcomes compared to the other models. 
