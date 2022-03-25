# Credit_Risk_Analysis
## Overview
The purpose of this analysis is to use my skills in Machine Learning algorithms to judge credit risk based on patterns learned through data. This project focused on Supervised Machine Learning. The data provided by LendingClub needs some resampling due to the fact that more members have good standing loans than risky loans. This data will hender unaccuarate results if machine learning algorithms aren't used. 

## Results
After loading in the original dataset, I used the column "loan_status" to determine rather the loan risk was high or low. 
![low_risk_vs_high_risk](https://user-images.githubusercontent.com/93167609/160065119-fe172ed4-d2d7-4352-865a-d0207ed255fe.png)

![split_test](https://user-images.githubusercontent.com/93167609/160065260-5ae92746-1b17-4675-8814-65cc15d4a865.png)

The original dataset has way more low risk applications than high. This will not lead to accurate predictions. 

### Oversampling
* RandomOverSampler model adds appropriate data to the set so both arguments are eqaul.

![counter](https://user-images.githubusercontent.com/93167609/160065490-140ae15f-c0da-4920-aab0-7198609822cd.png)

* Balanced Accuracy Score: 64%

![balanced_accuracy](https://user-images.githubusercontent.com/93167609/160065635-dece838e-e61b-4948-89fe-01c84e62d410.png)

* Precision: Overall- 99% High- 1% Low- 100%
* Recall: Overall- 60% High- 72% Low- 57%

![predicted_vs_actual](https://user-images.githubusercontent.com/93167609/160066033-c05a0022-d276-45d3-a7ef-b6e6a4d4f607.png)

![accuracy_report](https://user-images.githubusercontent.com/93167609/160067543-c6bfcf03-a2f1-48ba-84c4-26c76c6da763.png)

### Synthetic Minority Oversampling Technique
SMOTE model also adds approriate data from minority class not by random selection.

* Balanced Accurcay Score: 66% 

![SMOTE_balanced_accuracy](https://user-images.githubusercontent.com/93167609/160070626-26d7515c-d537-4c78-af89-dd5a20781911.png)

* Precision: Overall- 99% High- 1% Low- 100%
* Recall:Overall-69% High-63% Low- 69%

![SMOTE_low_vs_high](https://user-images.githubusercontent.com/93167609/160070780-8d015dc2-4900-4d27-aa94-c7c84c3b1738.png)

![SMOTE_accuracy_report](https://user-images.githubusercontent.com/93167609/160070819-db4aed03-9a54-40b0-b233-6393e1772d6c.png)

### Undersampling
Undersampling is best done using ClusterCentroids model
* Balance Accuracy Score: 54%

![Undersampling_accuracy](https://user-images.githubusercontent.com/93167609/160071392-bb549641-0b6c-4e28-a145-f6922bf8b3af.png)

* Precision: Overall- 99% High- 1% Low- 100%
* Recall: Overall- 40% High- 69% Low- 40%

![Undersampling_low_vs_high](https://user-images.githubusercontent.com/93167609/160072246-b33b383a-408d-4793-8f13-df856ee1e445.png)

![Undersampling_summary](https://user-images.githubusercontent.com/93167609/160072267-ba51c326-c084-4de7-a3d0-deffa6759aae.png)

### Combination Sampling
SMOTEENN model combines both under and over sampling. 

* Balance Accuracy Score: 64%

![Combo_accuracy](https://user-images.githubusercontent.com/93167609/160072575-437e69bb-74fe-4db5-9624-460e9dd3ded9.png)

* Precision: Overall- 99% High- 1% Low- 100%
* Recall: Overall- 57% High- 72% Low-57%

![Combo_low_vs_high](https://user-images.githubusercontent.com/93167609/160072695-35cdbdfe-023e-4771-b5cd-4a5389a391a7.png)

![Combo_summary](https://user-images.githubusercontent.com/93167609/160072723-92cd13e8-c937-4784-9180-541aafb8791a.png)

### Ensemble Learner
BalancedRandomForestClassifier model uses data of the same size and both minority and majority values. This model decreases risk of bias.

* Balance Accuracy Score: 79%

![Ensemble_balanced_accuracy](https://user-images.githubusercontent.com/93167609/160076375-6c85c01b-4dc3-4b6b-98c3-23cc53699db9.png)

* Precision: Overall- 99% High- 3% Low- 100%
* Recall: Overall- 87% High- 70% Low- 87%

![Ensemble_high_vs_low](https://user-images.githubusercontent.com/93167609/160076462-86b713d6-2746-4e48-886d-255a65b012bd.png)

![Ensemble_summary](https://user-images.githubusercontent.com/93167609/160076487-e961288f-8e79-425a-ab97-bc8f4b885c61.png)


Easy Ensemble AdaBoost Classifier model adds data to the set with individual decisions to classify new examples.
* Balance Accuracy Score: 93%

![Balanced_Ensemble_accuracy](https://user-images.githubusercontent.com/93167609/160174599-42bea3a6-ff20-4973-a867-d1fe2ab902e8.png)

* Precision: Overall- 99% High- 9% Low- 100%
* Recall: Overall- 94% High- 94% Low- 92%

![Balanced_Ensemble_low_vs_high](https://user-images.githubusercontent.com/93167609/160174759-661dc334-4fa3-4cb0-8bf3-19d7a3d94898.png)

![Balanced_Ensemble_summary](https://user-images.githubusercontent.com/93167609/160174796-9345b8c2-36e3-4c10-92ae-e6052fe77691.png)


## Summary
After reviewing all six models and their statistical analysis, the best model is the EasyEnsembleClassifier. This model yielded an overall accuracy rate of 94%. The overall recall rate was the highest amongst all the other models at 94%. The High risk accuarcy rate resulted in this model was the highest at 9%. This model resulted the best results, therefore I would recommend this model to perform a good credit risk analysis. +
