# 12th_Challenge

---

## Summary of Purpose  

This is not a program/app. 

This is just an analysis of which supervised machine-learning model is better at predicting the health of a loan for the given loan-data set. NOTE: my conclusions probably do not generalize to all loan-data sets.

---

## Overview of the Analysis

* Purpose: To determine the best model for classifying loans as risky.
* Data   : ~70k historical loans (I'm not sure whether or not this data is actually real)
  * Each row of this data includes  
    the classification of the loan (risky or safe),   
    the debt to income ratio of the borrower,  
    the number of accounts the borrower has  
    etc.
* I trained the models on 75% of the data (about 50k rows) & then tested the models on the remaining 25% of the data (about 20k rows).
* I prepared the data, created the models, fitted the data to the models, predicted the classifcations using the fitted models, & analyzed the performance of the models.
* I used the LogisticRegression() function for both models, but for one of the models, I used the RandomOverSampler() function to prep the data.

## Summary of Results

NOTE: 1 is the best score possible. 0 is the worst score possible.

* Regular Logistic Regression Model:
  * Balanced Accuracy Score: 0.9880
  * Stats for predicting `0` (healthy loan)
    * Precision: 1.00 | Recall: 1.00
  * Stats for predicting `1` (high-risk loan)
    * Precision: 0.87 | Recall: 0.98


* Oversampled Logistic Regression Model:
  * Balanced Accuracy Score: 0.9958
  * Stats for predicting `0` (healthy loan)
    * Precision: 1.00 | Recall: 0.99
  * Stats for predicting `1` (high-risk loan)
    * Precision: 0.87 | Recall: 1.00
    
## Conclusions

* I feel like there's enough data to say with reasonable certainty that the oversampled model is better.
* It's better because it has a higher recall for high-risk loans by 0.02. This lead is greater than its deficit of 0.01 in the recall for healthy loans. This 0.02 lead more than compensates for the 0.01 deficit. Furthermore, determining high-risk loans (which are less common than healthy loans) was the original goal of this Challenge, and the oversampled model is doing better at recalling those high-risk loans. Additionally, the oversampled model just has a higher balanced accuracy score.

Ultimately, the oversampled model has the slight edge over the non-oversampled model.

---
## Required/Compatible Technologies

**Compatible OS's:** Mac, Windows, or Linux  
**Programming language:** Python inside of Jupyter Lab  
**Required libraries:**  
  * numpy
  * pandas
  * pathlib
  * sklearn
  * imblearn
  * warnings (optional)

Using a conda environment from anaconda is preferable.

To view it, just look at it on github.

Alternatively, download the repository & open it with Jupyter Lab or some program that can run .ipynb files (e.g. VS Code using some extensions/add-ons). The cells should have already been run. If some haven't been run, then restart the kernel and run all the cells.

---

## Contributors

Noah Saleh

email: noahgsaleh@gmail.com

---
