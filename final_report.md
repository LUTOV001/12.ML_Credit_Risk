# ***UCB Module 12 Challenge Report***

## **Overview of the Analysis**

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
### The purpose of the challenge is to use a Machine Learning (ML) model used to predict the risk classification of a loan (e.g. Healthy or High-Risk) based on the provided original data for historic Loans and their features and to qualify the quality of the ML model by analyzing the accuracy of its predictions using ML metrics and analysis tools such as accuracy rate, the confusion matrix and classification reports.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## **Results**
---
Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  
 #### ![ML1 Classification Report](https://github.com/LUTOV001/12.ML_Credit_Risk/blob/main/Resources/ML_Model_1.jpg) 


#### 1. Healthy Loan (Class 0): Precision and f1 are both 100% and recall is almost as good (99%). While the spe at 91% indicates good performance identifying 'positives' (e.g. correctly predicting 0s as such) there could be improvements in identifying 'false positives', which could be accomplished by increasing the training data rate (we used the default 75% for this model) and/or changing the evaluation model (Logistic Regression was used).
#### 2. High Risk Loan (Class 1): Precision is 85% and f1 is 88%. While the spe at 99% indicates good performance identifying 'negatives' (e.g. correctly predicting 1s as such) there could be improvements in identifying 'false negatives'. This could be accomplished by increasing the training data rate (we used the default 75% for the original data set) and using a balanced data set
#### The IBA rate - which measures the model's accuracy taking into account class imbalance - looks good at 91% and 90% for class 0 and class 1 respectively, aligning with the other good ratios for Class 0, however, as discussed above, there is room for improvement for Class 1, therefore I recommend a resampling and balancing of the data to run an improved model.

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  
#### ![ML2 Classification Report](https://github.com/LUTOV001/12.ML_Credit_Risk/blob/main/Resources/ML_Model%20_2.jpg) 

#### 1. Healthy Loan (Class 0): Precision and f1 remained at 100% and recall also remained at 99% after the re-sampling excercise.Looking at the Confusion Matrix, there continued to be a high percentage of True Negatives and a low percentage of False Negatives, so the re-sampling did not impact the great rates we had for Class 0.
#### 2. High Risk Loan (Class 1): While precision fell 1 point to 84%, f1 improved 3 points to 91% and recall jumped 14 points to 99%. Additionally, looking at the confusion matrix, the 'True positive' rate remained high, improving from 563 to 615 (9% improvemnt) and there was an even better improvement on 'false negatives', declining from 56 to 4 (92% reduction). This overall proves that the resampling exercise improved the model significantly, more noticeably for Class 1.
---
## **Summary**

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

