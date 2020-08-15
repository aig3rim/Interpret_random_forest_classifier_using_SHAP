# Interpret_random_forest_classifier_using_SHAP

## Introduction

In this notebook I used Random Forest classifier and SHAP values to understand better customers and what can be done in the next campaign to increase CVR (Conversion Rate). After conducting EDA, I got the following business questions:
What kind of characteristics have people who placed a deposit?
What kind of characteristics have people who did NOT place a deposit?
Based on the available data, what can be done next time to increase CVR?

## Data
I used a public [dataset](https://www.kaggle.com/volodymyrgavrysh/bank-marketing-campaigns-dataset/data) with results of Portugal bank marketing campaigns. Conducted campaigns were based mostly on direct phone calls, offering bank client to place a term deposit. If after all marking afforts client had agreed to place deposit - target variable marked 'yes', otherwise 'no'.

## Motivation
I was curious to apply SHAP values to interpret a classification model obtained by training Random Forest. Also, this notebook is a part of [Data Scientist Nanodegree Program](https://www.udacity.com/course/data-scientist-nanodegree--nd025) provided by [Udacity](https://www.udacity.com).

## Getting started
You need an installation of Python, plus the following libraries:
* numpy
* pandas
* matplotlib.pyplot
* seaborn
* scikit-learn
* shap

## Main findings and answers to the business questions
1) What kind of characteristics have people who placed a deposit?
* last contact duration longer than 500 seconds
* have euribor3m values 1 and 2
* nr.employed <= 5100
* emp.var.rate <=0

2) What kind of characteristics have people who did NOT place a deposit?
* last contact duration less than 500 seconds
* have euribor3m values 4 and 5
* nr.employed >=5100
* emp.var.rate >= 0

3) Based on the available data, is there any opportunity to increase CVR?
Based on the SHAP waterfall plot, the most important feature is duration (last contact duration, in seconds), which contributes by more than 30% to the model's explainability. Therefore, having a relatively long last contact duration (> 500 seconds) may increase CVR.

**Note**: This analysis was done to grasp a practical understanding of applying SHAP values and Random Forest classifier. All the findings may do not have any connection with the real situation for placing a deposit. Also, we saw some parameters such as euribor3m, emp.var.rate, cons.price.idx, cons.conf.idx, nr.employed, which need an additional understanding of how they were derived and what are clear definitions for them.
