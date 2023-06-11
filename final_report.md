# ***UCB Module 12 : Credit Risk Challenge Report***
---
## **Overview of the Analysis**
#### The purpose of the challenge is to create a Machine Learning (ML) model to predict the risk classification of a loan (e.g. Healthy or High-Risk) based on the provided historic loan data set (e.g. original data) which containds loand details and features. After preparing and running the ML model we need to measure the quality of the predictions by analyzing their accuracy and using other ML model quality metrics and tools such as the confusion matrix and classification reports.
#### The original data contains the following loan features: Loan size, Interest rate, Debt-to-Income Ratio, Number of Accounts, Number of Derogatory Marks, Total Debt and the Loan Status; it is the Loan Status that the model will have to predict based on all the other features. This is considered a classification prediction, as the Loan Status is a binary feature which qualifies the loan as either 'Healthy' (Class 0)  or 'High-Risk' (Class 1) and it is for this reason that we will use the Logistics Regression model, specifically utilzing  the [LinearRegression model from scikit](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html#sklearn.linear_model.LogisticRegression).
#### As per the quality and stats of the original dataset, it contains over 77K records with the features listed above. In terms of the feature to predict - Loan Status - the data set is not balanced, as 97% of the 77,536 total records are of Class 0 (Healthy) and only 3% are of Class 1 (High-Risk); this imbalance in the data sample suggests that it will be more difficult to train the ML Model to properly predict Class 1 cases than for Class 0 with this original data set.
#### From the risk perspective, optimization of Class 1 "True Negative" predictions is very important and so is reduction of Class 0 "False Positives", as they hint at blindspots in the model failing to anticipate loans going wrong.
#### On the other hand, accurately predicting Class 0 "True Positives" has a revenue impact as these form the bulk of Healthly loans being serviced and providing the main source of income. As per Class 1 predictions, minimizing "False Negatives" to avoid revenue loss due to excessive loan declines is also relevant.
#### ***We will look at both Risk and Revenue - prioritizing the former- while analyzing the ML model predictions***

### ***Model 1 - Original Data***
#### > Using the original data set as-is (e.g. unbalanced), create a Logistics Regression model to predict the Loan Status classifiction for future loans by:
#### > Creating the model and fitting it to the original data set
#### > Training the model (*Note: We are using the default Training/Test split of 75/25)* 
#### > Test the model by generating the class predictions
#### > Qualify the prediction results by measuring/generating and analyzing accuracy, Confussion Matrix and the Classification (Imbalanced) Report
### ***Model 2 - Resampling/Balanced Classification***
#### > Using the [RandomOversampler module from the imbalanced-learn library](https://imbalanced-learn.org/stable/generated/imblearn.over_sampling.RandomOverSampler.html) resample the loan data and create a Logistics Regression model to predict the Loan Status classifiction for future loans by:
#### > Creating the model
#### > Run Resampling and ensure the classes are now balanced - e.g. Class 0 and Class 1 counts are equal
#### > Fit the model to the resampled data set
#### > Training the model (*Note: We will continue to use the default Training/Test split of 75/25)* 
#### > Test the model by generating the class predictions
#### > Qualify the prediction results by measuring/generating and analyzing accuracy, Confussion Matrix and the Classification Report
---
## **Results**
#### Below are the key results and analysis of the two ML models 

#### ***Machine Learning Model 1 (Original Data):***
#### *Confusion Matrix*
#### [[18663  , 102]
#### [   56   , 563]]

#### The first row of the matrix shows that 18,663 instances were correctly classified as positive, and 102 instances were incorrectly classified as negative. 
#### The second row of the matrix shows that 56 instances were incorrectly classified as positive, and 563 instances were correctly classified as negative.
#### We can see that due to the imbalance in the original data set, Class 1 metrics are not as good as Class 0, as shown by the 102 'False Negatives'.

#### *Classification Imbalanced Report*  
#### ![ML1 Classification Report](https://github.com/LUTOV001/12.ML_Credit_Risk/blob/main/Resources/ML_Model_1.jpg) 

#### While the overall model accuracy is 95%, we need to look at the detailed results by class: 
#### *1. Healthy Loan (Class 0):* Precision and F1 are both 100% and recall is almost as good (99%). While the SPE at 91% indicates good performance identifying 'positives' (e.g. correctly predicting 0s as such) there could be improvements in identifying 'false positives', which could be accomplished by increasing the training data rate (we used the default 75% for this model) and/or changing the evaluation model (Logistic Regression was used).
#### *2. High Risk Loan (Class 1):* Precision is 85% and f1 is 88%. While the spe at 99% indicates good performance identifying 'negatives' (e.g. correctly predicting 1s as such) there could be improvements in identifying 'false negatives'. This could be accomplished by increasing the training data rate (we used the default 75% for the original data set) and using a balanced data set
#### The IBA rate - which measures the model's accuracy taking into account class imbalance - looks good at 91% and 90% for class 0 and class 1 respectively, aligning with the other good ratios for Class 0, however, as discussed above, there is room for improvement for Class 1, therefore I recommend a resampling and balancing of the data to run an improved model.

#### ***Machine Learning Model 2 (Re-sampled/Balanced Data):***

#### *Confusion Matrix*
#### [[18649   , 116]
#### [    4   , 615]]

#### The first row of the matrix shows that 18,649 instances were correctly classified as positive, and 116 instances were incorrectly classified as negative. 
#### The second row of the matrix shows that 4 instances were incorrectly classified as positive, and 615 instances were correctly classified as negative.
#### We can see the impact of a balanced data set: 
#### The 'True negative' rate remained high, improving from 563 to 615 (9% improvement). On the down side, for 'False Negatives', there was a 13% increase in cases (from 102 to 116)
  
#### ![ML2 Classification Report](https://github.com/LUTOV001/12.ML_Credit_Risk/blob/main/Resources/ML_Model%20_2.jpg) 

#### While the overall model accuracy is now 99% after resampling, let's look at the detailed results by class: 
#### *1. Healthy Loan (Class 0):* Precision and F1 remained at 100% and recall also remained at 99%. Looking at the Confusion Matrix, there continued to be a high percentage of 'True Negatives' and a low percentage of False Positives, so the re-sampling did not impact the great rates we had for Class 0 and in fact, improved the "False positive" count, as explained above.
#### *2. High Risk Loan (Class 1):* While precision fell 1 point to 84%, F1 improved 3 points to 91% and recall jumped 14 points to 99%. Interpretation of metrics and conclusions follow below.
---
## **Summary**

#### In conclusion, looking at the models from both the ***Risk*** and ***Revenue*** perspectives, the resampling and rebalancing of the model proved benefitial on both areas: 

#### *Risk :* Besides improving the overall accuracy of the model by 4 points, the resampling improved the counts on risk relevant categories by improving the "True Negative" counts by 9% with very low impact (-1%) on 'True Positive" counts and a reduction of 96% on "False Positives".

#### *Revenue :* As mentioned above, minimal impact on the main revenue driver "True Positives" (-1%) and while it increased the case of cases driving revenue loss - e.g.'False Negatives' this comes as the downside of operating with a lower risk profile with the 96% reduction on  "False Positive" counts.

#### For the reasons listed above, ***we recommend using the Resample/Balance model which priorotizes operations with a lower risk profile without significant revenue impacts.***
---
### **Credits**
#### Prepared by Luis Torres 
#### [LUTOV001](https://github.com/LUTOV001)
#### June 2023