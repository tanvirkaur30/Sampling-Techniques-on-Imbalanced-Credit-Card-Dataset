# Sampling Techniques on Imbalanced Credit Card Dataset

---

## Objective
The objective of this assignment is to understand the importance of sampling techniques in handling highly imbalanced datasets and to analyze how different sampling strategies affect the performance of various machine learning models.

---

## Dataset Description

| Attribute        | Description                  |
|------------------|------------------------------|
| Dataset Type     | Tabular, Numerical           |
| Learning Type    | Supervised Learning          |
| Problem Type     | Binary Classification        |
| Target Column    | Class                        |
| Class Labels     | 0 → Normal, 1 → Fraud        |
| Nature           | Highly Imbalanced            |

The dataset contains anonymized numerical transaction features and represents real-world credit card fraud detection data.

---

## Problem Statement
Highly imbalanced datasets can severely bias machine learning models toward the majority class.  
This assignment focuses on balancing the dataset, applying different sampling techniques, and evaluating their impact on multiple machine learning models.

---

## Methodology

### Step 1: Dataset Loading
The dataset is downloaded and uploaded locally into Google Colab for analysis.

---

### Step 2: Dataset Balancing
To address class imbalance, **random undersampling** is applied to the majority class to create a balanced dataset with equal class representation.

---

### Step 3: Sampling Techniques Used

| Sampling ID | Technique Name                | Purpose                          |
|-------------|-------------------------------|----------------------------------|
| Sampling1   | Simple Random Sampling        | Baseline comparison              |
| Sampling2   | Systematic Sampling           | Ordered selection analysis       |
| Sampling3   | Stratified Sampling           | Preserve class distribution     |
| Sampling4   | Bootstrap Sampling            | Sampling with replacement        |
| Sampling5   | Stratified Sampling (Balanced)| Stable split on balanced data    |


**Cross-Validation Usage:**  
Cross-validation is used to evaluate model performance and generalization ability. Stratified k-fold cross-validation is applied to maintain class distribution across folds, which is important for the highly imbalanced nature of the dataset. Cross-validation is used only for evaluation and not for dataset balancing or sampling.


**Exclusion of Cluster Sampling:**  
Cluster sampling is not used because the dataset does not contain naturally defined clusters. Each transaction is independent, and creating artificial clusters could distort the class distribution. Therefore, cluster sampling is not suitable for this dataset.

---

### Step 4: Machine Learning Models

| Model ID | Algorithm              |
|----------|------------------------|
| M1       | Logistic Regression    |
| M2       | Decision Tree          |
| M3       | Random Forest          |
| M4       | K-Nearest Neighbors    |
| M5       | Naive Bayes            |


---

### Step 5: Evaluation Method
- Metric Used: **Accuracy**
- Each model is trained and tested using all five sampling techniques.
- Results are recorded for comparison.

---

## Results

### Accuracy Comparison Table

| Model | Sampling1 | Sampling2 | Sampling3 | Sampling4 | Sampling5 |
|-------|-----------|-----------|-----------|-----------|-----------|
| M1    | 83.33     | 66.67     | 50.00     | 83.33     | 50.00     |
| M2    | 83.33     | 66.67     | 66.67     | 66.67     | 66.67     |
| M3    | 50.00     | 66.67     | 50.00     | 66.67     | 50.00     |
| M4    | 50.00     | 33.33     | 50.00     | 33.33     | 50.00     |
| M5    | 66.67     | 33.33     | 16.67     | 66.67     | 16.67     |

---

### Best Sampling Technique per Model

| Model | Best Sampling Technique(s)              |
|-------|-----------------------------------------|
| M1    | Sampling1, Sampling4                    |
| M2    | Sampling1                               |
| M3    | Sampling2, Sampling4                    |
| M4    | Sampling1, Sampling3, Sampling5         |
| M5    | Sampling1, Sampling4                    |


> In cases of equal accuracy, multiple best sampling techniques are reported.

---

## Result Analysis
- Simple random and stratified sampling produced stable performance across most models.
- Systematic sampling showed inconsistent results for minority-sensitive classifiers.
- Bootstrap sampling demonstrated variance but increased overfitting risk.
- Accuracy values appear discrete due to reduced dataset size after undersampling.

---

## Conclusion
This experiment demonstrates that:
- Sampling strategies significantly impact model performance on imbalanced datasets.
- No single sampling technique performs best for all models.
- Stratified approaches provide reliable and consistent results.
- Proper dataset balancing is essential before applying sampling techniques.

---

## Tools & Libraries

| Tool           | Purpose                     |
|----------------|-----------------------------|
| Python         | Programming                 |
| Pandas         | Data handling               |
| NumPy          | Numerical computation       |
| Scikit-learn   | ML models & metrics         |
| Google Colab   | Execution environment       |

---

## Author
**Tanvir Kaur**  
Predictive Analysis – Sampling Assignment
