# Predicting Diabetes

## Overview
This repository contains resources and code for analyzing whether or not survey responses can be used to predict diabetes using machine learning. Exploratory data analysis was performed on the dataset seeking to understand any trends in the data. Multiple classification models were employed including Logistic Regression, KNN, and Random Forest. Various feature engineering and optimization strategies were applied to the models in an attempt ot improve model performance. 

## Data
Within the repository, you will find a resources directory containing CSV datasets and an SQL database. The datasets include various attributes related to diabetes, such as demographic information, medical history, lifestyle factors, and health outcomes.

The primary dataset, Diabetes Health Indicators, was sourced from kaggle and includes information recorded from the Behavior Risk Factor Surveillance System (BRFSS) survey. The BRFSS is the nation's premier system of health related telephone surveys. The dataset from kaggle cleaned and categorized this extensive survey to be used for diabetes and machine learning. The dataset included 253,680 rows, 22 features, and was classified based on positive or negative diabetes diagnosis.

The secondary dataset, Diabetes Predictions, was sourced from kaggle and includes basic demographic, behavioral, and health information as well as results from actual medical tests used to diagnose diabetes. The dataset includes 100,000 rows, 9 features, and was classified based on positive or negative diabetes diagnosis. 

## Models
There are six Jupyter Notebook files in this repository containing exploratory data analysis or different machine learning models:

1.  Logistic_Regression_Model: This notebook contains code for training and evaluating a logistic regression model on the primary diabetes data set(Diabetes Health Indicators).
2. KNN: This notebook implements a K-Nearest Neighbors (KNN) model for classification tasks using the primary diabetes data (Diabetes Health Indicators).
3. RandomForest: The third notebook demonstrates the usage of a Random Forest classifier for predicting diabetes-related outcomes with the primary data set (Diabetes Health Indicators).
4. EDA_Primary: This notebook contains the exploratory data analysis for the primary data set (Diabetes Health Indicators). 
5. EDA_Secondary: This notebook contains exploratory data analysis for the secondary data set (Diabetes Prediction) which contained features obtained  in a medical setting.
6. RandomForest_Secondary: This notebook contains the random forest model for the secondary data set (Diabetes Prediction).

## Primary Model Performance
Each model has been evaluated based on various metrics and performance indicators. The results of these evaluations are summarized below:

### Logistic Regression Model: 
A logistic regression model was employed to attempt to predict if a survey respondent would diagnosed with diabetes or not. In our analysis, we initially deployed a model with all features scaled, which resulted in a precision of 0.53 and a recall of 0.15 for the positive diabetes class. After applying data scaling techniques, we observed no significant improvement in model performance. However, upon incorporating feature engineering, specifically by introducing new interaction terms derived from existing features, we achieved slight enhancements in the model's predictive capabilities. The inclusion of these engineered features led to a higher precision of 0.56 for the positive diabetes class. These results suggest that scaling the data and feature engineering played a slight role in refining the model's ability to accurately classify instances, particularly in identifying positive cases.

![alt text](https://github.com/alexandriaorvis/predicting_diabetes/blob/main/Resources/Images/Optimized_KNN.png)

### KNN Model: 
A K Nearest Neighbors (KNN) model was employed to attempt to predict if a survey respondent would be diagnosed with diabetes or not. All features were scaled and we used 500 for the value of k (k=500). Ultimately, the number of neighbors didn't have a large impact on the results of the model. 500 seemed to be in the middle of the sweet spot. Multiple techniques were utilized to try to improve the model's accuracy including removing columns, adding new columns via feature engineering, and outliers were removed from the BMI data. 
A classification model was produced and had the following results:

![alt text](https://github.com/alexandriaorvis/predicting_diabetes/blob/main/Resources/Images/Optimized_LR.png)

Similar to the other models the results indicate that the model was good at predicting cases with no diabetes, but not very successful at predicting positive diabetes cases.

### Random Forest Model: 
A random forest model was employed to attempt to predict if a survey respondent would be diagnosed with diabetes or not. The first iteration of the Random Forest model scaled all features and was run with 500 estimators. The model was attempted with fewer and greater estimators with declining results either way. 
Feature importance was determined with the ‘feature_importances_’ function, and indicated that ‘BMI,’ ‘Age,’ ‘Income,’ ‘PhysHlth,’ and ‘GenHlth,’ were the most important features in this model. 
A classification model was produced and had the following results: 

![alt text](https://github.com/alexandriaorvis/predicting_diabetes/blob/main/Resources/Images/Optimized_RF.png)

These results indicate that while the model is good at predicting cases where the survey respondents didn’t have diabetes, it largely failed to categorize true diabetes cases as positive cases. 
The Random Forest Model was then modified to attempt to improve its ability to capture positive diabetes cases from survey responses. 

-Only continuous variables were scaled (‘BMI,’ ‘PhysHlth,’ ‘MentHlth’).\
-Less important features were dropped.\
-A number of new features were created.\
-Categorical variables were converted to dummy variables.


### Primary Model Conclusion

None of these attempts at optimizing the model were successful in significantly increasing the model’s ability to capture true diabetes cases. Though the model produced 86% accuracy it should be noted that the model almost always predicting no diabetes, and the high accuracy model was actually the result of an imbalanced dataset.

## Secondary Dataset Analysis

Given the poor performance of the primary model a secondary dataset was also evaluated, which included specific medical data typically used to diagnose diabetes.

### Random Forest Model

Similar optimization and feature engineering were applied to a Random Forest model on this secondary dataset. The model performed much better than the models for the primary dataset including a 97% overall accuracy, 92% precision, and 72% recall for people with diabetes. This outcome is unsurprising given the high correlation between medical diagnostic tools for diabetes and positive diabetes diagnosis.

![alt text](https://github.com/alexandriaorvis/predicting_diabetes/blob/main/Resources/Images/Optimized_RF_secondary.png)

## Final Analysis
In conclusion, all models used on the primary dataset performed with almost identical success. The model that technically performed the best was the Logistic Regression model following optimization. However, all models poorly identified positive diabetes cases. In answer to our original question, these results would indicate that this particular survey would not be able to successfully identify postive diabetes cases. The secondary dataset, however, has a high level of success in positively identifying diabetes cases. This would seem to indicate that medical data pertaining to diabetes diagnosis would be a much more reliable predictor than the survey data used. 


## Data Sources
- Diabetes Health Indicators Dataset (primary dataset)
  - https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset/data
- Diabetes Prediction Dataset (secondary dataset)
  - https://www.kaggle.com/datasets/iammustafatz/diabetes-prediction-dataset

## Other Resources
- https://www.almabetter.com/bytes/tutorials/data-science/exploratory-data-analysis

