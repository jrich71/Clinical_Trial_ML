# AIDS Clinical Trial: PCA, Clustering, and Classification Analysis

This project explored an AIDS clinical trial dataset using dimensionality reduction, clustering, and classification techniques. The goal is to identify patterns in patient data and evaluate models for predicting treatment outcomes.

---

## 📁 Dataset

- Source: UCI dataset at [https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175](https://archive.ics.uci.edu/dataset/890/aids+clinical+trials+group+study+175)
- Dataset Read: Downloaded to a CSV and then pulled via Google Drive using read_csv()
- Structure: Patient-level clinical and demographic variables from a randomized trial
- Target: Death or non-death binary (`cid`), used ased for exploratory clustering and classification tasks

---

## 🎯 Objectives

- Investigate feature relationships and multicollinearity
- Apply PCA for dimensionality reduction
- Use KMeans clustering to explore potential groupings
- Evaluate multiple classifiers to predict patient group labels

---

## 🧪 Key Methods

### 🔍 Multicollinearity Analysis
- Used correlation matrix and **Variance Inflation Factor (VIF)**
- Dropped features `str2` and `z30` due to high collinearity
- Retained `strat` after its VIF dropped below threshold when `str2` was removed

### 🔻 PCA (Principal Component Analysis)
- Reduced dimensions for exploratory visualization (2D, 3D)
- First 3 components explained ~36% of the total variance
- Used PCA output as input to clustering and visualization

### 🧩 KMeans Clustering
- Conducted elbow method analysis for optimal `k`
- Clustered data into **3 clusters** based on PCA output
- Plotted cluster membership in PCA-reduced space

### 🤖 Classification Models
Trained and evaluated multiple models to classify patient labels:

- Logistic Regression (with regularization)
- Decision Tree
- Random Forest
- ExtraTrees
- SVM (RBF Kernel)
- KNN
- Gradient Boosting
- AdaBoost

Evaluation used:
- **Weighted F1 Score**
- **Confusion Matrix Visualizations**

---

## 🧠 Findings & Next Steps

- PCA explained a modest portion of variance; clusters may not fully reflect data structure
- Logistic regression and ensemble methods performed reasonably well
- Future improvements:
  - Consider nonlinear dimensionality reduction (e.g., UMAP)
  - Explore other clinical outcome targets (e.g., survival)
  - Add feature importance analysis for interpretability
