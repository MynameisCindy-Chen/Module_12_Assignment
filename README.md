# Module 12 Report

## Overview of the Analysis

For this assignment, I will need to predict and verify if borrowers are having high-risk loan or healthy loan. 

Here are the information for each borrower listed in imported file that I am going to use to apply to models:

- Loan Size: Maxinum loan amount
- Interest Rate: The interest rate that borrower need to pay
- Borrower Income: Combined annual income of all mortgagees. 
- Debt-to-Income: It's a ratio for a personal finance measure that compares an individual's monthly debt payment to their monthly gross income.
- Number of Accounts: Numbers of bank accounts they own
- Derogatory Marks: Negative, long-lasting indications on the credit reports that generally mean you didn't pay back a loan as agreed.
- Total Debt: The total amount of loan left off to pay
Loan Status: 0 is healthy loan, 1 is high-risk loan

In this dataset, I will use some model to do train and test to predict borrower should be defined as healthy loan or high-risk loan. Loan status(y variable) is a significant variable to be used for prediction. The rest of factors are X variable.

In this assignment, the first thing I did is spliting the data by X and y variable, and count the total value of healthy loan(0) and high-risk loan(1). Accounding to my result, loan status is an imbalanced data. Healthy loan outnumber risky loan. Then I use train_test_split to seperate the data by 75% training dataset, 25% testing dataset in default. After that, I start doing my testing and see which model is more situation for this creidt risk analysis.
 - The first model I apply is logistic regression model, I get prediction data from this model. Afterwards, I use prediction and y_test to get the accuracy score, confusion matrix and classification report. Those % represent the accuracy of my model for prediction

 - Since y variable is imblanced, I use RandomOverSampler module to balance the data then I use logistic regression model to do testing and prection again. Once logistic regression model is applied, I generate accuracy score, confusion martix and classification report again. The percentage results are different. 


 ## Results

 * Machine Learning Model 1: Logistic Regression model only

    - Balanced accuracy score: The acurracy on predicting loan status is 95%, it can say we can 95% trust this model to predict if borrower's loan is in good status.
    - Precision: It is correct 85% of the time to predict borrower has high-risk loan out of all loan owners who actually have risky loan.
    - Recall: it is correct 91% of the time to predict borrower has high-risk loan out of all borrowers either actually have healthy loan or risky loan.

* Machine Learning Model 2: Random Oversampler module with Logistic Regression model

    - Balanced accuracy score: The acurracy on predicting loan status is 99%, it can say we can 99% trust this model to predict if borrower's loan is in good status.
    - Precision: It is correct 84% of the time to predict borrower has high-risk loan out of all loan owners who actually have risky loan.
    - Recall: it is correct 99% of the time to predict borrower has high-risk loan out of all borrowers either actually have healthy loan or risky loan.

## Summary

According to the accuracy score and classification report, Machine learning model 2 perform better in general because most of % are higher compared with model 1. However, the most significant percentage is precision, the goal is to lower False Positive(someone has risky loan but test result is healthy loan), it is more dangerous to categorize people who actually have risky loan as healthy loan owner. In my own opinion, I will pick model 1 because precision is higher. 

Somehow these 2 models are performing better on predicting healthy loan, but the most important to predict accurately is risky loan. These models also works, precision 84% and 85% are not bad. In my opinion, I also want to try RandomUnderSampler to see if this can bring a higher % on precision compared with RandomOverSampler. If we reduce the test and training sample, it might have a very different result. This is a exactly opposite way with oversampling model.