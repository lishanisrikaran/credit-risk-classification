# Credit Risk Classification Report 

## Analysis Overview 

This analysis aims to evaluate the reliability of two machine learning models created which can classify a 'unseen' loan as being healthy or high-risk.

The supervised machine learning models produced were trained on labeled prehistoric lending data, below are a list of features that were included in this training data:
- Loan size
- Interest rate
- Borrower's total debt
- Borrower income
- Borrower's debt to income ratio
- Number of accounts
- Derogatory marks

The models observed the above loan features against the loan status (healthy or high risk) they were associated with. 

The models now have the ability to classify a unseen loan as healthy or high risk if it provided with the associated features of the loan. However, a model of this importance cannot be implemented without being throughrougly evaluated and validated, therefore, this analysis will review the two machine learning models created.

The lending data containd 75,036 healthy loans and 2,500 high-risk loans. Within the original training data, there were 56,277 loans labelled as being healthy, and 1,875 as being high-risk. Based on this dataset alone, the classes used to train the first model were quite imbalanced. This could potentially cause a model bias towards the healthy loans which means the model may not be as good at generalising, especially for high-risk loans as they are the minority. However, the second algorithm produced addresses this imbalance to observe it's affect of the model's performance. 

Logistic regression was used to develop the classifier model, it is a linear statistical model which helps predict a categorical outcome. Each data point receives a probability of being a healthy or high-risk loan. If the probability is above a certain threshold, that data point is predicted to be a high-risk loan and any below the thesehold would be considered a healthy loan. 

Whilst developing this machine learning algorithm, several stages were followed:
1) Preprocessing
During preprocessing, the lending dataset was reviewed for any missing values. Once the dataset was confirmed to be 'cleaned', it was loaded in and the features and target variable were segregated. The feature and target variable values were then split into a training set and a testing set whereby the class proportions were maintained, this was done so that once the model was trained, it's performance could be evaluated against unseen loans to see how well it generalises. 
2) Training
A large subset of the labelled training data was used to teach the logistic regression model to recognise classification patterns. The model was provided with the features of the training data set and each of their loan statuses so that the model could compute a probability of the loan status and determine a categorisation threshold.
3) Validating
The remainder of the lending data which was split into the test set was then used to help validate the model to see how well the model is able to predict the loan status of loans which were unfamilar to it. The evaluation of this is outlined in the results section below.
4) Predicting
After the results evaluation and further piloting has concluded, the model will have been validated and can be used to predict the loan status of a loan accurately. 

As previosuly mentioned, during the first model, the target variables were unbalanced. Therefore, the same steps were applied to the second model but with with one additional step during preprocessing. The training data used was resampled using a random over sampler model which balanced out the class observations.

## Results

* Machine Learning Model 1:

Confusion Matrix:
- Of the 19,384 total loans predicted using the test set:
- 80 healthy loans were incorrectly classed as high risk (false positives).
- 67 high-risk loans were incorrectly classed as healthy (false negatives).
- The remaining 19,237 loans were correctly classified by the model.

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

---------------------------------------------------------------------------------------------------------------------------------------------
* Machine Learning Model 2:

Confusion Matrix:
- Of the 19,384 total loans predicted using the test set:
- 91 healthy loans were incorrectly classed as high risk (false positives).
- 2 high-risk loans were incorrectly classed as healthy (false negatives).
- The remaining 19,291 loans were correctly classified by the model.

Accuracy: 
[Increased from model 1]
- To reiterate, the balanced accuracy score helps to display how often the model has correctly predicted the loan status for both healthy and high-risk loans.
- The balanced accuracy score was 1.00 (2.s.f), or 100% (2.s.f).
- This score indicates that the model is always accurate at classifying whether an unseen loan is healthy or high risk.
- By using the 'balanced' score, the model has been proven to be accurate not only at predicting the majority class (healthy loans) but also the minority class (high-risk loans).
- Overall, this score provides confidence in this model's ability to generalise. 

Precision:
[Precision remained the same as model 1]
- To reiterate, precision measures the accuracy of positive predictions amongst all predicted positive observations.
- The classification report returned a precision of 1.00 for healthy loans, this indicates that all positive predictions for healthy loans were accurate for the test data the model was provided with. 
- The classification report returned a precision of 0.87 for high risk loans, this is still fairly high but the model has classified 13% of the predicted high-risk loans incorrectly. This means 13% of the high-risk loans classifications were actually healthy but the model classed them as high-risk (false positives).
- These findings indicate that the model could be piloted but it would need to undergo further training to increase the precision of classifying high risk loans correctly so that false positives are kept minimal.

Recall:
[Recall has remained the same as model 1 for healthy loans but increased for high-risk loans in comparison with model 1]
- To reiterate, recall measures the accuracy of positive predictions amongst all actual positive observations.
- The classification report returned a recall of 1.00 for healthy loans, this indicates that all positive predictions for healthy loans were accurate for the test data the model was provided with. 
- The classification report returned a recall of 1.00 for high risk loans, unlike the first model, this means model 2 has eliminated all false negative results; no actual high-risk loans were classified as being healthy. 
- These findings are ideal. 

F1-Score:
- To reiterate, the combined accuracy and precision is conveyed in the f1-score, this score helps evaluate the model's ability to keep false positives and false negatives minimal. 
- Combined, the healthy loans and high risk loans had a f1-score of 1.00 which indicates the model is optimal at predicting loan statuses. 
- However, the f1-score of high-risk loans has slightly weighed down this overall rating, the high-risk obtained a f1-score of 0.93, this could be improved so that high-risk loans avoid false positives.

## Summary

From the two classifier models evaluated, model 2 appears to perform better overall. This is because it classified 54 less loan statuses incorrectly compared to model 1. This caused the overall F1-score to increase from 0.99 (in model 1) to 1.00 (in model 2) due to model 2's increased performance in deflecting false negatives whereby actual high-risk loans are never classified as being healthy which is ideal for the company and their forecasts. 

However, it should be made clear that false positives are equally as important to deflect, if not more so in this context. This is because if a loan is classified as high-risk but is actually healthy, it has significant impacts to the indiviudal who is taking out this loan aswell as the peer to peer lending services company. The individual's credit score rating could potentially be impacted by this misclassification which could prevent them from taking out another loan or negatively impact the terms they are offered as they are considered 'high-risk', this can impact their life decisions which are often the underlying reason for taking out a loan such as a mortgage or business endevor. For this very reason the lending service may also be negatively impacted as the individual may move to a different service due to their treatment or more importantly, the peer to peer lending services company may not comform to industry regulations which can have graver financial/ legal impacts for them.   

In another context, model 2's performance improvement from model 1 could be enough to put this model forward into practice as it is very accurate. However, as the importance of the classification has the ability to impact a individual and their finances, no model is recommended at this stage. Model 2 predicted 11 more false positives in comparison with model 1 which displays more due dilligence is possible whilst training the model. The recommendation is that model 2 is further explored to reduce the false positives before it can be put into practice. 

