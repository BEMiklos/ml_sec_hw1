# Security of Machine Learning - Home Work 1.

**1.1. What is the average accuracy of the trained model on the test data when s = $2^{14}$?**

We trained the model for 10 epochs on a 70-30 train-validation split of the provided training dataset.
The mean accuracy observed on the test set is 99.49%.

**1.2. What is the model TPR, TNR, FPR, FNR, and AUC on the test data? What can be concluded from these about the model performance?**


| Metric  | Score  |
|---------|--------|
| TPR     | 0.9949 |
| TNR     | 0.9949 |
| FPR     | 0.0051 |
| FNR     | 0.0051 |
| ROC AUC | 0.9949 |

Based on the results, the predictions are well balanced, highly accurate, and the model has a good precision on the test set.

**2.1. Results with random adversary suffix for baseline attack**

Using different length of suffixes the accuracy of the attack (% of the malware samples are predicted benign) differs:
| Suffix% | Attack. acc. |
|---------|--------------|
| 5%      | 0%           |
| 10%     | 0%           |
| 15%     | 2%           |
| 20%     | 0%           |

The results above are expected as the original model was not overfitted, so it should be somewhat robust to random noise.

**2.2. Results with PGD attack on suffixes**
| Suffix% | Attack. acc. |
|---------|--------------|
| 5%      | 22%          |
| 10%     | 56%          |
| 15%     | 74%          |
| 20%     | 76%          |

Based on our results, increasing the ratio of the adversarial bytes relative to the original yields increasing attack accuracy, when attacking with PGD: $\epsilon=0.01$, for 100 epochs on each sample.

Furthermore, the mean length of the mask changes as follows:

|         |Mean. \|M\||
|---------|-----------|
| 5%      | 690.04    |
| 10%     | 1340.76   |
| 15%     | 1937.20   |
| 20%     | 2476.10   |

We also provide the attacked model - `model.pt` (saved in `task1.ipynb`) - along with the source code and README.



