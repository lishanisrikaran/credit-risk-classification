# Credit Risk Classification Report 

## Analysis Overview 

This analysis aims to evaluate the validity of two machine learning models created which can classify a 'unseen' loan as healthy or high-risk.

The supervised machine learning algorithms produced were trained on labeled prehistoric lending data, below are a list of features that were included in this data:
- Loan size
- Interest rate
- Borrower's total debt
- Borrower income
- Borrower's debt to income ratio
- Number of accounts
- Derogatory marks

The model observed the above loan features against the loan status (healthy or high risk) they were associated with. The algorithms now have the ability to classify a unseen loan as healthy or high risk loan status if it provided with the associated features of the loan. However, a model of this importance cannot be implemented without being throughrougly evaluated and validated, therefore, this analysis will review the two machine learning models created.

Within the lending data, there were 75,036 loans labelled as being healthy, and 2,500 as being high-risk. Based on this dataset alone, the classes used to train the first model were quite imbalanced. This could potentially cause a model bias towards the healthy loans which means the model may not be as good at generalising, especially for high-risk loans. However, the second algorithm produced addresses this imbalance to observe it's affect of the model's performance. 

Logistic regression was used to develop the classifier model, it is a linear statistical model which helps predict a categorical outcome. Each data point receives a probability of being a healthy or high-risk loan. If the probability is above a certain threshold, that data point is predicted to be a high-risk loan and any below the thesehold would be considered a healthy loan. 

Whilst developing this machine learning algorithms, logistic regress several stages were followed:
1) Preprocessing
During preprocessing, the lending dataset was reviewed for any missing values. Once the dataset was confirmed to be 'cleaned', it was loaded in and the features and target variable were segregated. The feature and target variable values were then split into a training set and a testing set whereby the class proportions were maintained, this was done so that once the model was trained, it's performance could be evaluated against unseen loans to see how well it generalises. 
2) Training
A large subset of the labelled training data was used to teach the logistic regression model to recognise classification patterns. The model was provided with the features of the training data set and each of their loan statuses so that the model could compute a probability of the loan status and determine a categorisation threshold.
3) Validating
The remainder of the lending data which was split into the test set was then used to help validate the model to see how well the model is able to predict the loan status of loans which were unfamilar to it. The evaluation of this is outlined in the results section below.
4) Predicting
After the results evaluation and further piloting has concluded, the model will have been validated and can be used to predict the loan status of a loan accuractly. 

As previosuly mentioned, during the first model, the target variables were unbalanced. Therefore, the same steps were applied to the second model but with with one additional step during preprocessing. The training data used was resampled using a random over sampler model which balanced out the class observations.

## Results

* Machine Learning Model 1:

Confusion Matrix:
- Of the 19,384 total loans predicted using the test set:
- 80 healthy loans were incorrectly classed as high risk (false positives).
- 67 high-risk loans were incorrectly classed as healthy (false negatives).
- The remaining 19,237 loans were correctly classified.

Accuracy:
- The balanced accuracy score helps to display how often the model has correctly predicted the loan status for both healthy and high-risk loans.
- The balanced accuracy score was 0.94 (2.s.f), or 94% (2.s.f).
- This score indicates that the model is highly accurate at classifying whether an unseen loan is healthy or high risk as it is quite close to  1.00.
- By using the 'balanced' score, the model has been proven to be accurate not only at predicting the majority class (healthy loans) but also the minority class (high-risk loans).
- It's important to note that this score suggests that 6 out of every 100 loans have been incorrectly classified. Further analysis is needed to understand the impact of these misclassifications.
- Overall, this score provides a positive indication for this model's ability to generalise. 

Precision:
- Precision measures the accuracy of positive predictions amongst all predicted positive observations.
- The classification report returned a precision of 1.00 for healthy loans, this indicates that all positive predictions for healthy loans were accurate for the test data the model was provided with. 
- The classification report returned a precision of 0.87 for high risk loans, this is still fairly high but the model has classified 13% of the predicted high-risk loans incorrectly. This means 13% of the high-risk loans classifications were actually healthy but the model classed them as high-risk (false positives).
- These findings indicate that the model could be piloted but it would need to undergo further training to increase the precision of classifying high risk loans correctly so that false positives are kept minimal.

Recall:
- Recall measures the accuracy of positive predictions amongst all actual positive observations.
- The classification report returned a recall of 1.00 for healthy loans, this indicates that all positive predictions for healthy loans were accurate for the test data the model was provided with. 
- The classification report returned a recall of 0.89 for high risk loans, this is still fairly high but the model has classified 11% of the actual high-risk loans incorrectly. This means 11% of the actual high-risk loans classifications were classified as healthy (false negatives).
- These findings indicate that the model could be piloted but it would need to undergo further training to increase the recall of classifying high risk loans correctly so that false negatives are kept minimal.

F1-Score:
- The combined accuracy and precision is conveyed in the f1-score, this score helps evaluate the model's ability to keep false positives and false negatives minimal. 
- Combined, the healthy loans and high risk loans had a f1-score of 0.99 which does an excellent job at predicting loan statuses. 
- However, the f1-score of high-risk loans has slightly weighed down this overall rating, the high-risk obtained a f1-score of 0.88, this could be improved so that high-risk loans avoid false positive and negatives.


* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
