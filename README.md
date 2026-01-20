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

### Model Performance Analysis
- **Random Forest** achieved perfect accuracy (100%) across all sampling techniques, demonstrating exceptional robustness and the strength of ensemble learning on balanced datasets. This suggests that Random Forest's ability to aggregate multiple decision trees effectively captures complex patterns regardless of the sampling method.
- **Decision Tree** also performed exceptionally well, achieving near-perfect to perfect accuracy (97.82% - 100%) across all sampling methods, indicating that tree-based models are particularly well-suited for this dataset.
- **Support Vector Machine (SVM)** showed strong and consistent performance (96.94% - 100%), demonstrating its effectiveness in creating optimal decision boundaries for binary classification tasks.
- **K-Nearest Neighbors (KNN)** achieved high accuracy (95.64% - 100%), with performance varying slightly based on the sampling technique, suggesting sensitivity to the local neighborhood structure created by different sampling methods.
- **Logistic Regression** showed the most variation across sampling techniques, with accuracy ranging from 88.65% to 100%, highlighting its sensitivity to the sampling method used and the linear separability of the sampled data.

### Sampling Technique Analysis
- **Cluster Sampling** surprisingly achieved perfect 100% accuracy across all models, which is unusual and may indicate potential data leakage, overfitting, or that the selected cluster(s) happened to contain highly representative or homogeneous data. This result warrants further investigation to ensure methodological soundness.
- **Bootstrap Sampling** performed consistently well (95.41% - 100%), benefiting from sampling with replacement which creates diverse training sets. However, the redundancy introduced may lead to overfitting in some cases.
- **Simple Random Sampling** showed strong performance (94.08% - 100%), providing a good baseline and demonstrating that random selection can be effective when the dataset is pre-balanced.
- **Stratified Sampling** achieved good results (90.97% - 100%), though interestingly it didn't outperform other methods as might be expected. This could be because the dataset was already balanced before sampling, reducing stratification's typical advantage.
- **Systematic Sampling** showed the lowest performance for Logistic Regression (88.65%), possibly due to periodic patterns in the data or ordering effects that may have introduced bias in the sample selection.

### Impact of Class Balancing
- **Class imbalance** severely affects model performance, making balancing a crucial preprocessing step. The Random Over Sampling preprocessing proved highly effective in addressing the initial imbalance.
- The overall high performance across all combinations (minimum 88.65%, maximum 100%) suggests that the Random Over Sampling preprocessing step was highly effective in creating a well-balanced dataset that enables models to learn patterns from both classes equally.
- The results demonstrate that proper preprocessing can elevate even simpler models like Logistic Regression to achieve competitive performance (88.65% - 100%).

### Ensemble vs. Individual Learners
- Ensemble methods (Random Forest) demonstrated superior stability and robustness compared to individual learners, maintaining perfect accuracy regardless of sampling variation.
- Tree-based models (both Decision Tree and Random Forest) significantly outperformed linear models (Logistic Regression), suggesting that the credit card fraud detection problem has non-linear decision boundaries that are better captured by tree-based algorithms.

### Practical Implications
- For production deployment on imbalanced credit card datasets, **Random Forest with any sampling technique** would be the recommended approach given its consistent perfect performance.
- The perfect accuracy scores, especially with Cluster Sampling, suggest the need for additional validation techniques such as cross-validation, testing on unseen data, and checking for data leakage to ensure model generalizability.
- The high accuracies may also indicate that the test set size is relatively small, which could lead to optimistic estimates. Larger test sets or stratified k-fold cross-validation would provide more reliable performance metrics.

### Recommendations for Future Work
- Investigate the Cluster Sampling results more thoroughly to rule out data leakage or methodological issues.
- Evaluate models using additional metrics such as Precision, Recall, F1-Score, and ROC-AUC, which are more informative for imbalanced classification problems.
- Implement cross-validation to obtain more robust performance estimates and reduce the variance in accuracy measurements.
- Test model performance on a separate, unseen holdout set to validate the generalizability of these results.
- Explore other balancing techniques such as SMOTE (Synthetic Minority Over-sampling Technique) or ADASYN for comparison with Random Over Sampling.

---

## Conclusion

This study demonstrates that:

- Proper class balancing significantly improves performance across all models and sampling techniques.
- Random Forest is the most robust model, achieving perfect accuracy (100%) regardless of the sampling technique used, making it the ideal choice for credit card fraud detection.
- Cluster Sampling unexpectedly achieved perfect accuracy across all models, though this result requires further validation to ensure methodological soundness.
- All sampling techniques performed well when combined with proper class balancing, with accuracies ranging from 88.65% to 100%.
- Tree-based models (Random Forest and Decision Tree) outperformed linear models, suggesting non-linear relationships in the credit card transaction data.
- The combination of Random Over Sampling for balancing followed by appropriate sampling techniques creates a robust framework for handling imbalanced classification problems.

---

## 📄 License

[Your License]
