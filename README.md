# Credit_Risk_Analysis
## Overview of the Analysis
The purpose of this analysis was to utilize supervised machine learning in order to distinguish good loans from risky loans.  Since good loans outnumber risky loans, credit risk is an unbalanced classification problem.  Therefore, in order to determine the best way to classify credit risk, multiple techniques were used in training and evaluating models with unbalanced classes.  Then the accuracy of these techniques can be compared against eachother, to show which technique presents the most accurate evaluation.
## Results
### Random Oversampling
![ROSAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/ROSAccuracy.PNG)
![ROSReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/ROSReport.PNG)
- Using random oversampling results in an accuracy score of approximately 0.629 or 62.9% accuracy.
- This model shows an incredibly low precision for high-risk with a precision of 0.01, while it shows very high precision for predicting low-risk loans with that precision being 1.00.  This means that loans categorized as low-risk are almost certainly low-risk, while loans categorized as high-risk only have a 1% chance of actually being high risk.
- In terms of Recall/Sensitivity this model had 57% sensitivity for high-risk and 68% sensitivity for low-risk.  This means that in both categories the rate of prediciting true positves was less than 70%

### SMOTE Oversampling
![SMOTEAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/SMOTEAccuracy.PNG)
![SMOTEReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/SMOTEReport.PNG)
- Using SMOTE oversampling results in an accuracy score of appoximately 0.628 or 62.8% accuracy, meaning it is almost identical in accuracy to random oversampling.
- This model also shows an incredibly low precision for high-risk with a precision of 0.01, while it shows very high precision for predicting low-risk loans with that precision being 1.00.
- In terms of Recall/Sensitivity this model had 62% sensitivity for high-risk and 63% sensitivity for low-risk.  So while there was a higher percentage of true positives for high-risk loans when compared to random oversampling, there was a lower percentage of true positives for low-risk loans.

### Undersampling
![CCAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/CCAccuracy.PNG)
![CCReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/CCReport.PNG)
- Using Cluster Centroids for undersampling results in an accuracy score of appoximately 0.510 or 51% accuracy
- The undersampling model also shows an incredibly low precision for high-risk with a precision of 0.01, while it shows very high precision for predicting low-risk loans with that precision being 1.00.
- For Recall/Sensitivity this model had 59% sensitivity for high-risk and 43% sensitivity for low-risk.  Meaning that when compared to both methods of oversampling, undersampling has significantly lower sensitivity.  In fact this method of sampling showed the lowest sensitivity of all methods tested.

### SMOTEEN Combination Sampling
![SMOTEENAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/SMOTEENAccuracy.PNG)
![SMOTEENReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/SMOTEENReport.PNG)
- Using SMOTEEN combination sampling results in an accuracy score of appoximately 0.655 or 65.5% accuracy
- Once again, this model shows a low precision for high-risk with a precision of 0.01, while it shows a high precision for predicting low-risk loans with that precision being 1.00.
- The Recall/Sensitivity of this model had 70% sensitivity for high-risk and 61% sensitivity for low-risk.  Therefore, of the models tested up to this point, this model has the highest sensitivity for prediciting high-risk loans.  However, since high-risk loans are such a small portion of the dataset as a whole, the average sensitivity for this model is still lower than both of the oversampling methods.

### Balanced Random Forest Classifier
![BRFCAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/BRFCAccuracy.PNG)
![BRFCReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/BRFCReport.PNG)
- Using the Balanced Random Forest Classifier results in an accuracy score of appoximately 0.788 or 78.8% accuracy
- This is the first model tested to show any change in precision for high-risk loans with a precision of 0.04, while it still shows a high precision for predicting low-risk loans with that precision being 1.00.
- The Recall/Sensitivity of this model had 67% sensitivity for high-risk and 91% sensitivity for low-risk.  While this is a slight decrease in sensitivity for high-risk loans when compared to the SMOTEEN sampling, it is a marked increase in the sensitivity for low-risk loans, leading to a much better average sensitivity of 91%.

### Easy Ensemble Classifier
![EEAccuracy](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/EEAccuracy.PNG)
![EEReport](https://github.com/conpm/Credit_Risk_Analysis/blob/main/Analysis/EEReport.PNG)
- Using the Easy Ensemble Classifier results in an accuracy score of appoximately 0.925 or 92.5% accuracy
- This model shows the highest tested precision for high-risk loans with a precision of 0.07, and it still maintains a high precision for predicting low-risk loans with that precision being 1.00.
- The Recall/Sensitivity of this model is also the strongest performing with a 91% sensitivity for high-risk and 94% sensitivity for low-risk.
- Based on all three metrics of accuracy, precision and recall/sensitivity, this is the best performing model.

## Summary
Based on these results we can see that out of the sampling methods that were tested in this analysis the best performing was the Easy Ensemble Classifier, which performed the best in every category and showed substantially higher accuracy than all the other methods.  However, since the precision scores were so low for prediciting high-risk loans across all methods, it seems unlikely that any of these methods would be truly accurate in classifying low and high-risk loans.  It seems that since such a small portion of the data is classified as high-risk that none of these models can have a very high precision for predicting high-risk loans.  Since we already knew going into the analysis that good loans greatly outnumber risky loans, these datasets do not do much to further our understanding of what qualifies a risky loan.  In order to get a more accurate analysis of good vs risky loans, it seems plausible that a Scaler could be applied to the data in order to get a more accurate comparison of the two loan types.
