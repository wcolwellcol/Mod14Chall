# Mod14Chall

## Overview of the Analysis

The purpose of this exercise was to train a trading bot utilizing machine learning to see if it could identify a profitable trading strategy. First, a baseline test is established utilizing short and long simple moving average values. Our bot is trained and tested on the same dataset, but utilizing in-sample and out of sample windows.

SVC classifier Model:
The baseline windows I started with were 4 days for the short window and 100 days for the long window. I also started by with a training-test split of 3 months. These windows and splits were subsequently changed

DecisionTreeClassifier:
The decision tree classifier overall is a less reliable strategy than the SVC classifier baseline model and that same model tuned. Compared to both base case and tuned parameters, the decision tree unilaterally performed worse across different test cases.

![Short window of 4, long window of 120, training 6 months](https://github.com/wcolwellcol/Mod14Chall/blob/main/images/DT6sw4lw120.png)

![Optimal set up](https://github.com/wcolwellcol/Mod14Chall/blob/main/images/DToptimal.png)




## Results

Below are the accuracies, precision and recall scores for each of my models. Note the declined performance for the Decision Tree Model.

* SVC Model Baseline 3 months Training (short=4 long=100):
  * Balanced Accuracy: 0.55
  * Performance on -1s:
    * Precision: .43
    * Recall: 0.04
  * Performance on 1s:
    * Precision: .56
    * Recall: .96

* SVC Model 6 months Training (short=4 long=100)
  * Balanced Accuracy: 0.56
  * Performance on -1s:
    * Precision: .44
    * Recall: 0.02
  * Performance on 1s:
    * Precision: .56
    * Recall: .98

* SVC Model 6 months Training (short=3 long=120)
  * Balanced Accuracy: 0.55
  * Performance on -1s:
    * Precision: .39
    * Recall: 0.03
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

Answers to tuning questions:

Overall, lengthening the amount of training time for the ML model translated into improved returns. Decreasing the window had an adverse effect, as I don't think the model had enough time to learn and was basically throwing random darts at a dartboard.

Changing the SMA windows had varying results. Overall, I found my initial setup of a short window of 4 and a long window of 100 worked best. Both increasing and decreasing either window seemed to have an unpredictable effect for me. I tried lengthening both, shortening both, mixing up the two, and found that a 4 and 100 set up was my best attempt. I'm sure there is a more optimal mix out there but I could not find it given my time constraints.

The best result is captured below.
![6 months of training, short window of 4, longwindow of 100](https://github.com/wcolwellcol/Mod14Chall/blob/main/images/SVC6.png)

