# Credit_Risk_Analysis

## Overview
- The purpose of the analysis is to evaluate different machine learning models and determine which one is a better model to predict credit risk.

- Since the majority of the loans are good loans, the number of risky loans is easily outnumbered.  Therefore, different approaches are adopted to train the machine learning models to reduce bias so the credit risk predictions would be more accurate. 

## Results
- Naive Random Oversampling
![NRO_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/NRO_Acc.png)
![NRO_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/NRO_CM.png)
  - The balanced accuracy score is 63.7%.
  - The precision score for high risk loan is 1.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 62% and for low risk loan is 65%.

- SMOTE Oversampling
![SMOTE_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/SMOTE_Acc.png)
![SMOTE_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/SMOTE_CM.png)
  - The balanced accuracy score is 63.0%.
  - The precision score for high risk loan is 1.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 62% and for low risk loan is 64%.

- Cluster Centroids Undersampling
![CC_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/CC_Acc.png)
![CC_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/CC_CM.png)
  - The balanced accuracy score is 63.0%.
  - The precision score for high risk loan is 1.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 59% and for low risk loan is 43%.

- SMOTEENN
![SMOTEENN_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN_Acc.png)
![SMOTEENN_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/SMOTEENN_CM.png)
  - The balanced accuracy score is 51.0%.
  - The precision score for high risk loan is 1.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 71% and for low risk loan is 59%.

- Balanced Random Forest Classifier
![BRF_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/BRF_Acc.png)
![BRF_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/BRF_CM.png)
  - The balanced accuracy score is 79.6%.
  - The precision score for high risk loan is 4.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 68% and for low risk loan is 91%.


- Easy Ensemble AdaBoost Classifier
![EEAB_Acc](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/EEAB_Acc.png)
![EEAB_CM](https://github.com/SzeWingChan/Credit_Risk_Analysis/blob/main/Resources/EEAB_CM.png)
  - The balanced accuracy score is 92.5%.
  - The precision score for high risk loan is 7.0% and for low risk loan is 100%.
  - The recall score for high risk loan is 91% and for low risk loan is 94%.

## Summary
- Out of all six machine learning models, SMOTEENN model has the lowest balanced accuracy score (51.0%) and Easy Ensemble AdaBoost Classifier model has the highest balanced accuracy score (92.5%).  The balanced accuracy scores of the rest of the models are between 63.0% and 79.6%.
- All models have a 100% precision score for low risk loan, which means when the model predicts the credit risk is low for a loan, it is correct every time.  But the precision scores for high risk loan for all models is very low (between 1.0% and 7.0%), meaning that all models are bad at predicting if a loan is actually a high risk one.  
- The F1 sores (harmonic mean) of low risk loan is between 60.0% and 97.0% and this suggests the models handle the predictions for low risk loan well.  However, the F1 scores for high risk loan varied between 1% and 14% and this means the success rate of recognizing a loan is risky is low.
- When evaluating if the machine learning model is good at predicting credit risk, we must bear in mind the dataset is heavily imbalanced (i.e.  good loans outnumber risk ones).  We cannot simply judge the models by its accuracy score and must review how well it predicts both low/high risk loans individually (by reviewing precision scores and F1 scores).  
- Compare to the ability to identify loans as low risk, the ability to flag high risk loans is more impactful as these loans have adverse impact to the company.
- All six models fail to predict credit risk, despite some models perform better than the others.  Therefore, it is not recommended to use any of them alone to predict credit risk at this stage.
