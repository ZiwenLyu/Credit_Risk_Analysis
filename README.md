# Credit_Risk_Analysis

## Overview of the analysis
This project is to process and analyze the loan data from LendingClub, a peer-to-peer lending services company, then train the model to predict the potential credit card risk. I will first prepare the data by dropping unnecessary data, labeling string type data, and scaling the data. As the redit risk is an inherently unbalanced classification problem, as good loans easily outnumber risky loans, I will apply random oversampling, SMOTEE, undersampling, and SMOTEENN to find out a better resampling technique to adjust the unbalanced dataset. Next, I will compare two supervised machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk and comment on their performances.

## Results: 
### Resampling
- Naive Random Oversampling 
- ![native random oversampling](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/naive_random_oversampling_result.png)

The overall accuracy score is 53.3%. Since the high risk prediction is more significant to our case, here we can see the high risk precision is 1% and the recall rate is 70%.

- SMOTEE Oversampling 
- ![SMOTEE Oversampling](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/SMOTE_oversampling_result.png)

The overall accuracy score is 63.9%. The high risk precision is 1%, and the recall rate is 65%.

- Undersampling 
- ![undersampling](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/undersampling_result.png)

The overall accuracy score is 57.0%. The high risk precision is 1%, and the recall rate is 59%.

- SMOTEENN 
- ![SMOTEENN](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/SMOTEENN_result.png)

The overall accuracy score is 57%. The high risk precision is 1%, and the recall rate is 74%.

Here, all four model's high-risk precision are low, only 1%. So we compare the recall rate. In the credit risk case, we will pick the resampling model with the highest recall rate because it means it has less false negative predictions. In other words, less high-risk custoemrs will not be predicted as low risk. So here I chose the SMOTEENN for resampling.

### Machine Learning Models
- Balanced random forest classifier
- ![balanced random forest classifier](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/balanced_random_forest_classifier.png)

After apply SMOTEENN resampling, the model's  overall accuracy score is 99.6%. The precision of high-risk prediction is 75%, and the recall is 27%.

- Easy ensemble adaboost classifier
- ![easy ensemble adaboost classifier](https://github.com/ZiwenLyu/Credit_Risk_Analysis/blob/main/screenshots/easy_ensemble_adaboost_classifier_result.png)

The model's overall accuracy score is 98.2%. The precision of high-risk prediction is 13%, and the recall is 41%.

By comparing the two learning models we can see that, the first one is high precision and low recall, and the second one is low precision and high recall. In this case, to avoid more risks and reduce costs for the company, I will suggest to use the second model. Because we would rather refuse some low credit risk clients than miss any high credit risk clients, it's better to pick the second model with relatively higher recall rate.

## Summary: 
Tthe SMOTEENN resampling and easy ensemble adaboost classifier perform better recall rates in this case. In the further research, I recommend to try more classifier models such as desicion tree or adaptive boost for this data. 
