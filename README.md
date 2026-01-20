# Sampling Techniques on Imbalanced Credit Card Dataset

## Objective
The objective of this assignment is to understand the impact of different sampling techniques on a highly imbalanced dataset and to analyze how these techniques affect the performance of various machine learning models.

---

## Dataset
- **Dataset Name:** `Creditcard_data.csv`
- **Target Variable:** `Class`
- **Problem Type:** Binary Classification
- **Issue:** Highly imbalanced classes

---

## Class Balancing Strategy
Before applying sampling techniques, the dataset was converted into a balanced dataset using **Random Over Sampling**. This ensures that both classes have equal representation and avoids bias during model training.

---

## Sampling Techniques Used
After balancing the dataset, the following five statistical sampling techniques were applied:

1. **Simple Random Sampling**
2. **Systematic Sampling**
3. **Stratified Sampling**
4. **Cluster Sampling**
5. **Bootstrap Sampling**

Each sampling method generated a separate dataset sample.

---

## Machine Learning Models Used

| Model Code | Algorithm                  |
|------------|----------------------------|
| M1         | Logistic Regression        |
| M2         | K-Nearest Neighbors (KNN)  |
| M3         | Support Vector Machine (SVM)|
| M4         | Decision Tree              |
| M5         | Random Forest              |

All models were trained using a standardized pipeline and evaluated using accuracy score.

---

## Accuracy Results Table

| Sampling Technique    | M1 (LR) | M2 (KNN) | M3 (SVM) | M4 (DT)  | M5 (RF) |
|-----------------------|---------|----------|----------|----------|---------|
| Simple Random         | 94.08   | 97.51    | 97.82    | 99.38    | 100.0   |
| Systematic            | 88.65   | 96.51    | 96.94    | 98.25    | 100.0   |
| Stratified            | 90.97   | 95.64    | 97.51    | 97.82    | 100.0   |
| Cluster               | 100.00  | 100.00   | 100.00   | 100.00   | 100.0   |
| Bootstrap             | 95.41   | 98.69    | 98.69    | 99.56    | 100.0   |

---

## Best Performing Combinations

| Model                | Best Sampling Method  |
|----------------------|-----------------------|
| Logistic Regression  | Cluster Sampling      |
| KNN                  | Cluster Sampling      |
| SVM                  | Cluster Sampling      |
| Decision Tree        | Cluster Sampling      |
| Random Forest        | All Methods (Tied)    |

### Overall Best Technique: **Cluster Sampling**
### Overall Best Model: **Random Forest** (100% accuracy across all sampling methods)

---

## Discussion

- **Class imbalance** severely affects model performance, making balancing a crucial preprocessing step.
- **Random Forest** achieved perfect accuracy (100%) across all sampling techniques, demonstrating exceptional robustness and the strength of ensemble learning on balanced datasets.
- **Cluster Sampling** surprisingly achieved 100% accuracy across all models, suggesting that the selected cluster(s) captured representative patterns from the entire dataset.
- **Decision Tree** also performed exceptionally well, achieving near-perfect to perfect accuracy across all sampling methods.
- **Logistic Regression** showed more variation across sampling techniques, with accuracy ranging from 88.65% to 100%, highlighting its sensitivity to the sampling method used.
- The overall high performance across all combinations suggests that the Random Over Sampling preprocessing step was highly effective in addressing class imbalance.

---

## Conclusion

This study demonstrates that:

- Proper class balancing significantly improves performance.
- Random Forest is the most robust model, achieving perfect accuracy (100%) regardless of the sampling technique used.
- Cluster Sampling unexpectedly achieved perfect accuracy across all models, indicating that the cluster selection effectively represented the entire dataset.
- All sampling techniques performed well when combined with proper class balancing, with accuracies ranging from 88.65% to 100%.

---
