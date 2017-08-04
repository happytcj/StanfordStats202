# Final Report

## TJ Jiang

**tcjiang108@gmail.com**

SUID-0710

## Introduction
The goal of this project is to train a classification model and operate on a testing dataset

## Data Observation
Both training and test data files have been examined and no missing data are found. The training set has n=80046 observations and p=10 features. The testing set contains n=30001 observations and p=10 features. Both training and testing set contain features query_id and url_id, but they do not have any meaningful statistical significance that would be useful in modeling the relevance response variable. The response value for all observations are either 0 or 1.

Data selection: training data are divided into ten folds and cross validation is performed.

Todo: Divide training data randomly by positive and negative relevance.

"All positive training data are randomly divided into five folds of approximately equal sizes. So are the negative training data. The first fold of positive training data and the first fold of negative training data are grouped together, named Group 1. Similarly, rest of data forms Group 2 to Group 5."

Try to get training error down to about 32-34%. Without training set selection divided out between positive and negative relevance observations training error hovers above 38%

**Todo: Log, squareroot, square, combination for generation of new predictors**
Done: major improvement

**Todo: omitting a predictor/predictors**
omitting predictors with lower p-values did not improve validation error

**Todo: using the query_num and url_id variables**
Create new predictor using query_num: improved slightly

Todo: Feature selection
http://scikit-learn.org/stable/modules/feature_selection.html
By Variance: Did not work

## Random Forest:
.5% improvement in misclassification error by square root transforming sig1
.1% improvement in misclassification error by including query_num
sig3_tr is very important to classification accuracy
Leaving out is_homepage yields minor improvement

## KNN
Norm improves 3%
including is_home for KNN ~0.3% improvement

## Chat with Rajiv:
Grading will be mostly based on understanding and exploration of the classifier, not so much on results; < 33% should be good
SVM with default R settings yielded good results right off the bat
Normalize AND standardize data
