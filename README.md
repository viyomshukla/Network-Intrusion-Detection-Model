# Network Intrusion Detection using Machine Learning and Ensemble Methods

This repository contains information and a summary of a study comparing traditional machine learning and ensemble learning models for network intrusion detection using the NSL-KDD dataset.

## Study Overview

The study addresses the challenge of detecting network intrusions, particularly rare attack types, within the context of imbalanced data. The NSL-KDD dataset, containing over 113,000 network traffic records labeled as normal or belonging to four attack categories (DoS, Probe, R2L, U2R), was used for evaluation.

A key difficulty lies in the significant class imbalance, where normal traffic and Denial of Service (DoS) attacks are prevalent, while Remote-to-Local (R2L) and User-to-Root (U2R) attacks are infrequent and harder to detect.

## Data Preprocessing and Feature Engineering

The study employed several techniques to prepare the data for modeling:

* **Missing Value Handling:** Imputation methods were used to address any missing data points.
* **Categorical Feature Encoding:** Categorical features like protocol type, service, and flag were converted into numerical representations using label encoding and one-hot encoding.
* **Binary Subsets:** The dataset was divided into four binary classification problems, each aiming to distinguish normal traffic from one specific attack type.
* **Recursive Feature Elimination (RFE):** RFE was applied to each binary subset to select the most relevant features, reducing dimensionality and potentially improving model performance.
* **Synthetic Data Generation (cGANs):** To tackle the scarcity of Probe, R2L, and U2R attack samples, Conditional Generative Adversarial Networks (cGANs) were utilized to generate synthetic data, balancing the class distributions and aiding in better detection of these rare attacks.

## Models Evaluated

The study compared the performance of the following machine learning models:

**Traditional Models:**

* Support Vector Machine (SVM)
* Decision Tree
* Logistic Regression
* Random Forest

**Ensemble Models:**

* Random Forest
* Gradient Boosting Machine
* XGBoost

These models were trained on the preprocessed datasets, with synthetic data augmenting the minority attack classes.

## Performance Evaluation

Model performance was evaluated using standard classification metrics:

* Accuracy
* Precision
* Recall
* F1-score

## Key Findings

The study revealed several important insights:

* **Ensemble Model Superiority:** Ensemble learning models generally outperformed traditional machine learning models, particularly in the detection of rare and complex attack types like R2L and U2R.
* **XGBoost Performance:** Ensemble methods such as XGBoost achieved higher recall and F1-scores, indicating a better balance between sensitivity (correctly identifying attacks) and precision (avoiding false alarms).
* **Impact of Synthetic Data:** The generation and use of synthetic data significantly improved the detection rates for the minority attack classes, highlighting its importance in addressing class imbalance. However, the study noted that challenges persist with extremely scarce classes.
* **Effectiveness of Feature Selection:** Recursive Feature Elimination (RFE) proved effective in reducing the dimensionality of the data without negatively impacting model performance.

## Conclusion

The study concluded that a robust network intrusion detection framework can be built by combining ensemble learning techniques with targeted feature selection and synthetic data generation. While traditional models can perform adequately for common attack types, ensemble methods offer a significant advantage in handling complex and infrequent attacks.

This research provides a strong foundation for developing more adaptive and effective intrusion detection systems capable of addressing the evolving landscape of cybersecurity threats.
