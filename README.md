# Credit-risk-classification report

## Overview of the Analysis

The purpose of this analysis is to review a model that has been trained to assess loan risk.
We were provided with a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.
Features used in the model included:
loan size, interest rate, borrower income, debt to income, number of accounts, derogatory marks and total debt
Our target variable being loan status with 75036 healthy loan status ("0") and 2500 high risk loan status ("1").

In our analysis, we split the data into X_train, X_test, y_train and y_test using train_test_split, and used a logistic regression model fit with X_train and y_train. We then used the testing data X_test to make predictions.
The results from our first evaluation led us to look into oversampling our data. Please refer to the results below.

## Results

1- With an accuracy of 99% (not 100%), although close, the model does not predict accurately and there is room for error in our model. 

2- Thanks to the confusion matrix, we can see there are 56 false negatives and 102 false positive in our model. Neither of which is a good option as both leave opportunities for inaccuracy. 

3- Since we are dealing with a binary decision problem (healthy vs high-risk loans) we can use a classification report to assess our model and take a further look into the false negatives and false positives. According to our classification report:
    a- the logistic model does a pretty good job at predicting healthy loan, with a 100% precision, in other words there is a low false positive rate at predicting healthy loans. 
    b- on the other hand, there are higher chances of getting false positives when predicting high risk loans with a 85% precision. 

                  precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619

    accuracy                           0.99     19384
   macro avg       0.92      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384

4- A balanced accurary score of 95.2% tells us that there could be improvement in measuring accuracy between the "healthy" and "high risk" loans, which a more balanced sample might help us attain.

**** Oversampling ****

1- With a 99.36% balanced accuracy score, the logistic regression model, fit with oversampled data does a better job at balancing prediction between "healthy" and "high risk" loans.

2- However the overall accuracy of the model does not change at 99%, which means though minimal there is still room for error in our model. 

3- The confusion matrix with oversampled data shows:
 a- 4 false negatives which is an improvement compared to the 56 without oversampling, and 
 b- 116 false positives vs 102 without oversampling. 
 
4- The new classification report still confirms the logistic regression model predicts healthy loans better than the high risk loans.

              precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.84      0.99      0.91       619

    accuracy                           0.99     19384
   macro avg       0.92      0.99      0.95     19384
weighted avg       0.99      0.99      0.99     19384

## Summary

In conclusion, the logistic regression model performed better with oversampling data , however with the false negatives and false positives noticibly with the high risk loans, we would recommend exploring other prediction models.
