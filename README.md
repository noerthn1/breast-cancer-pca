# Principal Component Analysis (PCA) on Breast Cancer Dataset

## Overview
This project demonstrates the application of **Principal Component Analysis (PCA)** on a real-world medical dataset to reduce dimensionality while preserving most of the informative variance. The goal is to evaluate whether PCA can simplify the feature space without significantly degrading classification performance.

The **Breast Cancer Wisconsin dataset** is used, which contains multiple correlated numerical features describing tumor characteristics.

---

## Dataset
- **Source:** Scikit-learn built-in Breast Cancer Wisconsin dataset
- **Samples:** 569
- **Features:** 30 numerical features
- **Target:** Binary classification (malignant vs benign)

The dataset is well-suited for PCA due to strong correlations among features and differing feature scales.

---

## Project Workflow

### 1. Data Exploration
- Inspected dataset structure and feature distributions
- Verified absence of missing values
- Visualized feature correlations using a heatmap to justify PCA usage

### 2. Feature Scaling
- Standardized all features using **StandardScaler**
- Ensured zero mean and unit variance, which is essential for PCA

### 3. Explained Variance Analysis
- Applied PCA without limiting components
- Used a scree plot and cumulative explained variance to determine the optimal number of components
- Selected **10 principal components**, retaining approximately **95% of total variance**

### 4. Dimensionality Reduction
- Reduced feature space from 30 to 10 dimensions
- Visualized data using the first two principal components
- Observed clear structure and partial class separation

### 5. Model Comparison (With vs Without PCA)
- Trained a **Logistic Regression** model on:
  - Original scaled features
  - PCA-transformed features
- Compared classification performance on a held-out test set

**Result:**  
PCA significantly reduced dimensionality while achieving comparable predictive performance, demonstrating its effectiveness in simplifying models without major accuracy loss.

---

## Key Findings
- Many original features were highly correlated, causing redundancy
- PCA reduced feature dimensionality by ~66% while retaining most information
- Classification performance remained largely unchanged after PCA
- Reduced feature space leads to simpler and potentially faster models

---

## Limitations
- PCA components are linear combinations of original features, reducing interpretability
- PCA is unsupervised and does not consider class labels
- Some discriminative information may be lost if too few components are retained

---

## Future Improvements
- Compare PCA with supervised dimensionality reduction techniques (e.g., LDA)
- Evaluate performance with other classifiers (SVM, Random Forest)
- Use cross-validation to select the optimal number of components
- Explore non-linear dimensionality reduction methods such as Kernel PCA

---

## Technologies Used
- Python
- NumPy
- Pandas
- Matplotlib & Seaborn
- Scikit-learn
- Google Colab

---

## Conclusion
This project shows that **Principal Component Analysis is an effective dimensionality reduction technique for real-world datasets**, enabling simpler models while preserving most of the information required for accurate classification.
