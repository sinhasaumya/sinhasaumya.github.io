---
date: 2021-01-10
excerpt: "Using supervised learning to detect credit card fraud from PCA-transformed data and evaluating models. Data prep, exploration and machine learning using Python."
header: ~
tags:
  - credit card
  - fraud
  - python
title: "Credit Card Fraud Detection"
---

*Project submitted to BSA Datathon 2021.*  

*Quick links - [Dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud), [Kaggle notebook](https://www.kaggle.com/saumya94/credit-card-fraud-detection), [Github notebook](https://github.com/sinhasaumya/projects/blob/main/credit-card-fraud-detection.ipynb)*  

<iframe src="https://www.slideshare.net/slideshow/embed_code/key/fiLPyLIcJiHcbk" width="586" height="490" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"></div>  

  

According to the Australian Payment Fraud Report 2020, fraud losses on cards have consistently risen from 2010 to 2018 globally. However, good for Australia that the financial year 2018-19 saw a 20% reduction in the total value of card fraud even as the total value of card payments increased. Nonetheless, a whopping $ 464M were lost due to fraud. In the US, things are different - reports of credit card fraud rose by 72.4% in the same period as reported in Federal Trade Commission's Consumer Sentinel Network Data Book 2019.  

For any bank, card fraud has distressing repercussions: financial, reputational, loyalty and other brand-related. The sooner a bank can detect fraud, the better it is.  

Supervised learning will be used to train PCA-transformed credit card transaction data and build models to classify transactions unseen by the models into fraudulent and non-fraudulent. Further, the best performing model will be determined. The ideal model will detect as many as possible fraudulent cases correctly. The aim is to first detect as many as possible cases of fraud and then attempt to reduce misclassification of non-fraud cases. This translates to giving primary importance to high recall so that all cases of fraud in the dataset can be detected and secondary importance to high precision so proportion of cases the model says were fraud actually are fraud is maximized.  

The [dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud) was downloaded from Kaggle, and 80% of it was used for training whereas at the remaining 20% was reserved for testing. Further, 20% of the training data was used as validation set. As highlighted in the presentation above, [Kaggle notebook](https://www.kaggle.com/saumya94/credit-card-fraud-detection) and [Github notebook](https://github.com/sinhasaumya/projects/blob/main/credit-card-fraud-detection.ipynb), the dataset posed the challenges of imbalanced class, unscaled data and multicollinearity. The solutions to each are discussed below.  

The latter two problems were tackled first. Data was standardized and normalized, and it was found that final results were signigficantly better with standardization than with normalization. The Variane Inflation Factor (VIF) technique was used to check for multicollinearity. The column 'Amount' showed a VIF of ~12, an indicator of the presence of multicollinearity. This meant that there was a combination of other columns in the dataset that was strongly correlated to 'Amount', and thus the elimination of 'Amount' was necessary. With < 0.002% of fraud cases in the training data, class imbalance was considerable. This was dealt with at the time of data modelling with Logistic Regression, Decision Tree and Random Forest. Each of the models was fit to data that was subject to random undersampling, random oversampling, SMOTE (synthetic oversampling) and random oversampling followed by random undersampling. The model with best cross-validation scores and best performance on validation data were shortlisted.  

The obtained precision and recall on validation set are recorded below as (precision, recall) for each model after treating data for class imbalance.  

|                                           | No treatment | Random Undersampling | Random Oversampling | SMOTE (oversampling) | Random oversampling + undersampling |
|-------------------------------------------|--------------|----------------------|---------------------|----------------------|-------------------------------------|
| Logistic Regression with threshold moving | (0.84, 0.85) | (0.82, 0.7)          | (0.86, 0.85)        | (0.87, 0.85)         | (0.85, 0.86)                        |
| Decision Tree                             | (0.74, 0.76) | (0.01, 0.95)         | (0.78, 0.86)        | (0.4, 0.82)          | (0.86, 0.78)                        |
| Random Forest                             | (0.94, 0.84) | (0.04, 0.95)         | (0.96, 0.86)        | (0.9, 0.89)          | (0.96, 0.86)                        |


Random Forest with random oversampling, SMOTE and random oversampling + undersampling has presented precision and recall higher than any other. With 89% recall and 90% precision, Random Forest with SMOTE is the most desirable model according to the definition of 'ideal model' above.  

On the one hand, the best performing classifier Random Forest is a black-box model; as its internal working is not fully known, it is not fully explananble and interpretable. On the other hand, the white box model Logistic Regression has lower performance but is easily explanable and interpretable. Banks tend to prefer white box models for this reason. Therefore, the final model selection must be thought-out.




