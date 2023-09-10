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

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
