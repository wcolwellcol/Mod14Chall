# Mod14Chall

## Overview of the Analysis

The purpose of this exercise was to train a trading bot utilizing machine learning to see if it could identify a profitable trading strategy. First, a baseline test is established utilizing short and long simple moving average values. Our bot is trained and tested on the same dataset, but utilizing in-sample and out of sample windows.

SVC classifier Model:


DecisionTreeClassifier:
The decision tree classifier overall is a less reliable strategy than the SVC classifier baseline model and that same model tuned. As you can see in the image below, the decision tree actuall initially outperforms 




## Results

Below are the accuracies, precision and recall scores for each of my models. Note the declined performance for the Decision Tree Model.

* SVC Model Baseline:
  * Balanced Accuracy: 0.55
  * Performance on -1s:
    * Precision: .43
    * Recall: 0.04
  * Performance on 1s:
    * Precision: .56
    * Recall: .96


* Decision Tree Model:
  * Balanced Accuracy: .45
  * Performance on -1s:
    * Precision: .44 
    * Recall: 0.83 
  * Performance on 1s:
    * Precision: .54
    * Recall: .15


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

Summarizing the results of these models requires us to revisit the purpose of this exercise. In this particular use case, we are using machine learning to predict whether a loan has a high risk of defaulting or not. It is safe to assume that whoever utilizes this model would be far more concerned with defaults compared to healthy loans. In other words, falsely classifying a healthy loan as an unhealthy one is a less consequential mistake than falsely classifying an unhealthy loan as a healthy one. I mainly care about minimizing false negatives. For this, we must look at the recall score for the 1s group.

The second model which was fit on resampled data performed better according to the recall score for 1s. The second model has a recall of .99 for 1s, whereas the first model had a recall of .91. This does come with a marginal decrease in precision, but I am less sensitive to precision in this use case. Overall, 99/100 loans faulty loans being correctly identified seems to be strong enough to recommend implementing this model as part of the risk identification ecosystem. I would not solely rely on this model, however, if 1 defaulting loan would pose a substantial risk to the business.