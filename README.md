# Security of Machine Learning - Home Work 1.

**1.0 What is the average accuracy of the trained model on the test data when s = 214?**

The mean accuracy on the test set is 98.97%.

**1.1 What is the model TPR, TNR, FPR, FNR, and AUC on the test data? What can be concluded from these about the model performance?**

- TPR: 0.9897
- TNR: 0.9897
- FPR: 0.0102
- FNR: 0.0102

- ROC AUC: 0.9897

Based on the results, the predictions are well balanced, highly accurate, and has a good precision on the test set.

**2.0 Results with random adversary suffix for baseline attack**

Using different length of suffixes the accuracy of the attack differs:
 - 5% of the original length: 10% of the malware samples are predicted benign
 - 10%: 10% attack accuracy
 - 15%: 22% attack accuracy
 - 20%: 22% attack accuracy

A surprising result is that even a random suffix with the right length falsifies the results with 10-20% efficiency, while we measured quite high accuracy on the test set. This suggests that our model is still not robust enough.

**2.1 Results with PGD attack on suffixes**
 - 5%: 50% attack accuracy
 - 10%: 80% attack accuracy
 - 15%: 86% attack accuracy
 - 20%: 96% attack accuracy

Apparently, it is sufficient to apply the PGD algorithm only to the suffixes, the results can be falsified quite effectively with longer suffixes.



