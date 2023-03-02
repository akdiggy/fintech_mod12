# Module 12 Report Template

## Overview of the Analysis

Using the imbalanced-learn library, a logistic regression model to compare two versions of the dataset in the lending_data.csv file. Also, data will be resampled using the RandomOverSampler module from the same library. For both cases, you’ll get the count of the target classes, train a logistic regression classifier, calculate the balanced accuracy score, generate a confusion matrix, and generate a classification report.

The financial information in the lending_data.csv file contains the following data elements:

* loan_size
* interest_rate
* borrower_income 
* debt_to_income
* num_of_accounts
* derogatory_marks
* total_debt
* loan_status

The y data, the target variable, is the loan status. The X data, the features, are all of the columns above minus the loan status. The loan status has a value of either 0 (healthy loan) or 1 (high-risk loan). Given the features, a prediction is to be made for the loan status. In the initial Dataframe, there are 75036 0's and 2500 1's. 

The logistic regression stages that we undergone for this exercise were:
* prepare the data
* split the data into training and testing sets
* create a model (to be able to start predicting)
* train the model 
* predict (classify features with the model)
* predict (test the model on new data)

Some of the methods used for the above process are:
* value_counts
* train_test_split
* LogisticRegression
* fit
* classification_report_imabalanced


## Results

* Machine Learning Model 1 (using original data):
  * The balanced accuracy score is 0.9520479254722232. It is used to evaluate how good a binary classifier is. In this case, the classes are imbalanced because there are way more healthy loans in the dataset versus high-risk loans. Given the confusion matrix, it was very accurate in detecting the true positives and the true negatives. That is represented in the 95% score for this model. 
  * The precision values for this model are 1.0 for the healthy loans and 0.85 for the high-risk ones. This measures how the model correctly made the positive predictions for the true positives and true negatives. 
  * The recall values for this model are 0.99 for the healthy loans and 0.91 for the high-risk ones. This measures the number of actually true positives divided by the sum of the true positives and false negatives. 


* Machine Learning Model 2 (using resampled data):
  * The balanced accuracy score is 0.9936781215845847. Given the confusion matrix, it was just slightly less accurate with the true positives. However, it had more true negatives and less false positives and false negatives. That is indicative of the 99% value for this model. 
  * The precision values for this model are 1.00 for the healthy loans and 0.84 for the high-risk ones. These percentages are very similar to Model 1. 
  * The recall values for this model are both 0.99 for both types of loans. This model has a better value in comparison to Model 1 being close to perfect at 99%. 


## Summary

Model 2 appears to perform better than model 1 given the higher balanced accuracy score and recall value. The precision values in both models are practically identical. This model also has a better confusion matrix than model 1. 
