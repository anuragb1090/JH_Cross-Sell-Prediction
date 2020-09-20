# JH_Cross-Sell-Prediction
This repo is for the Analytics Vidhya competition of Cross-Sell Prediction.

This is my first attempt at documenting my approach towards a Janata Hack competition so if something is confusing, please don't hesitate to ask and I will do my best to clarify.

## General Process
- I started off with EDA and understanding how the categorical and numerical variables behave wrt 'Response'. My initial models binned the numerical variables but I decided to go with continuous data instead when scores started to improve.
- Categorical data were encoded using custom mappings. I did not use Label Encoding as I wanted to preserve the hierarchy of variables. And did not opt for One-Hot-Encoding(OHE) as that would have exploded the number of features. Maybe time and private leaderboard will tell if I was wrong with not going with OHE.
- I experimented with many models some being CatBoost, LightGBM, XGBoost etc. LightGBMClassifier performed the best. Will be curious to know what my fellow competitors preferred.
- LGBMClassifier performed the best when L2 regularization was performed. I tried hyperparameter optimization using grid search but did not get satisfactory results. Looking back I should have increased number of CV or maybe performed random search.

## Feature Engineering
- Manual mapping were assigned to categorical variables to preserve the hierarchy among the features.
- Initially I binned numerical variables as the EDA showed that there was a distinction among the numerical features between 0s and 1s which would have helped prediction. But as competition progressed, I realised it's better to remove binning and use as continuous features instead.
- LGBMClassifier performed the best among all models. I manually tuned hyperparameters to get high scores.
