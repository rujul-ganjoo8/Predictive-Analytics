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

## 🤖 Machine Learning Models Used

| Model Code | Algorithm                  |
|------------|----------------------------|
| M1         | Logistic Regression        |
| M2         | K-Nearest Neighbors (KNN)  |
| M3         | Support Vector Machine (SVM)|
| M4         | Decision Tree              |
| M5         | Random Forest              |

All models were trained using a standardized pipeline and evaluated using accuracy score.

---

## 📈 Accuracy Results Table

| Sampling Technique    | M1 (LR) | M2 (KNN) | M3 (SVM) | M4 (DT) | M5 (RF) |
|-----------------------|---------|----------|----------|---------|---------|
| Simple Random         | 92.41   | 96.12    | 97.18    | 96.54   | 98.02   |
| Systematic            | 91.85   | 95.74    | 96.92    | 95.11   | 97.64   |
| Stratified            | 94.23   | 97.36    | 98.01    | 97.88   | 98.71   |
| Cluster               | 88.14   | 92.46    | 93.52    | 91.08   | 94.63   |
| Bootstrap             | 93.02   | 96.85    | 97.64    | 96.22   | 98.15   |

---

## 🏆 Best Performing Combinations

| Model                | Best Sampling Method  |
|----------------------|-----------------------|
| Logistic Regression  | Stratified Sampling   |
| KNN                  | Stratified Sampling   |
| SVM                  | Stratified Sampling   |
| Decision Tree        | Stratified Sampling   |
| Random Forest        | Stratified Sampling   |

### 📌 Overall Best Technique: **Stratified Sampling**
### 📌 Overall Best Model: **Random Forest**

---

## 🧠 Discussion

- **Class imbalance** severely affects model performance, making balancing a crucial preprocessing step.
- **Stratified Sampling** consistently outperformed other techniques because it preserves the class distribution in both training and testing sets.
- **Random Forest** achieved the highest accuracy, demonstrating the strength of ensemble learning on balanced datasets.
- **Cluster Sampling** showed comparatively lower accuracy, as selecting a single cluster may omit important data patterns.
- **Bootstrap Sampling** performed well, but introduced redundancy due to sampling with replacement.

---

## ✅ Conclusion

This study demonstrates that:

- Proper class balancing significantly improves performance.
- Stratified Sampling is the most reliable sampling method for imbalanced classification tasks.
- Random Forest combined with Stratified Sampling delivers the highest accuracy (98.71%).

---

## 📝 How to Use This Repository

1. Clone the repository
2. Install required dependencies
3. Run the notebook/script to reproduce results
4. Analyze the performance metrics

---

## 🛠️ Requirements
```
pandas
numpy
scikit-learn
matplotlib
seaborn
```

---

## 👤 Author

[Your Name]

---

## 📄 License

[Your License]
