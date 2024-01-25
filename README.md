# First ML Ops Kaggle Competition - Playground season 4 episode 1

## Competition Goal

To predict whether a customer continues with their account or closes it (e.g., churns).

## Evaluation Method

Submissions are evaluated on area under the ROC curve between the predicted probability and the observed target.

## General Flow description

### Compared EDA

First step was to do a compared EDA, which you can find [here](/Compared_EDA.ipynb). The objective was to try and find differences between train and test set, so that we could differenciate the train output to perform better - No significant differences were found. 

### First Model

As it was the first try, I did a short EDA of train set, transformed categorical into dummie variables and scaled numerical variables using Robust, Standar and MinMax scaler depending on the outliers and distrubution of the variable.
Next step was to perform a first approach using boosting ML models such as lightgbm, xgboost, randomforest and gradient boosting with a gridsearch cross-validacion method (cv=5) to optimize the models, scoring by roc_auc_score as it is the challenge score parameter.
Once I got the best classifier (XGboost), I went for a feature data selection, itering all columns to find the best match.
Finally, I took this last model and re-trained it with the hole train data and predicted the test data to submit my first try.
You can find the step by step [here](/First_Model.ipynb).

### Second Model

Second model followed similar steps as the first one but I tried under and oversampling the not Exited values as the proportion is 20/80%. Without good results, I changed the variable 'Balance' into categorical (0 for no balance and 1 for balance). 
Lastly, I performed feature selection and hiperparameter tunning at the same time.
You can find the step by step [here](/Second_Model.ipynb).

### Third Model

Third model went through the same steps as the second one, without over and undersampling but I added a dataset partition by 2 columns, hoping this could lead to 3 better performing models. The selected partition columns were IsActiveMember and HasCrCard.
You can find the step by step [here](/Third_Model.ipynb).

### Fourth Model

Same as second model but only using the catboost model.
You can find the step by step [here](/Fourth_Model.ipynb).

### Deep Learning Model

Lastly, I introduced deep learning tecnology using Tensorflow, which did not give me better results than catboost but had a much better time performance.
You can find the step by step [here](/DL_Model.ipynb).

