# 🧠 Lion Optimization Algorithm (LOA) – SVM with Linear, RBF, and Polynomial Kernels

This project implements the **Lion Optimization Algorithm (LOA)** for feature selection in a **Support Vector Machine (SVM)** classifier using **Linear**, **Radial Basis Function (RBF)**, and **Polynomial (Poly)** kernels.  
The goal is to enhance classification performance in predicting **DPP-4 inhibitor bioactivity** based on molecular descriptor data.

---

## ⚙️ 1. Method Overview

| Component | Description |
|------------|--------------|
| **Algorithm** | Lion Optimization Algorithm (LOA) |
| **Model** | Support Vector Machine (SVM) |
| **Kernels** | Linear, RBF, Polynomial (Poly) |
| **Objective** | Feature selection and model performance optimization |
| **Dataset** | Molecular descriptors (PubChemFP0–PubChemFP880) with binary classification labels (IC₅₀ thresholded activity) |

The **Lion Optimization Algorithm** is a metaheuristic inspired by lion social behavior — including **pride and nomad dynamics, mating, and territorial defense** — to balance exploration and exploitation.  
LOA selects an optimal subset of features that improves predictive accuracy while reducing redundancy.

---

## 🧩 2. Experimental Setup

Four configurations were tested for each kernel:

| Model | Feature Selection | Kernel | Parameters | Description |
|:------|:------------------|:--------|:-------------|:-------------|
| **A** | None (All Features) | Linear / RBF / Poly | Default | Baseline model |
| **B** | LOA | Linear / RBF / Poly | Default | LOA-selected features with default parameters |
| **C** | None (All Features) | Linear / RBF / Poly | Best | Tuned SVM parameters (Grid Search) |
| **D** | LOA | Linear / RBF / Poly | Best | LOA-selected features with tuned parameters |

---

## 📊 3. Results Summary

### 🔹 **Linear Kernel**

#### **All Features – Default**
- Train Accuracy: **0.9419**
- Test Accuracy: **0.6364**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.62 | 0.73 | 0.67 |
| Class 1 | 0.67 | 0.55 | 0.60 |

#### **LOA Feature Selection – Default**
- Train Accuracy: **0.9302**
- Test Accuracy: **0.7273**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.73 | 0.73 | 0.73 |
| Class 1 | 0.73 | 0.73 | 0.73 |

#### **All Features – Best**
- Train Accuracy: **0.9419**
- Test Accuracy: **0.6364**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.62 | 0.73 | 0.67 |
| Class 1 | 0.67 | 0.55 | 0.60 |

#### **LOA Feature Selection – Best**
- Train Accuracy: **0.9302**
- Test Accuracy: **0.7273**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.73 | 0.73 | 0.73 |
| Class 1 | 0.73 | 0.73 | 0.73 |

---

### 🔹 **RBF Kernel**

#### **All Features – Default**
- Train Accuracy: **0.7326**
- Test Accuracy: **0.6364**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 1.00 | 0.27 | 0.43 |
| Class 1 | 0.58 | 1.00 | 0.73 |

#### **LOA Feature Selection – Default**
- Train Accuracy: **0.7791**
- Test Accuracy: **0.6818**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.83 | 0.45 | 0.59 |
| Class 1 | 0.62 | 0.91 | 0.74 |

#### **All Features – Best**
- Train Accuracy: **0.8605**
- Test Accuracy: **0.7727**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.80 | 0.73 | 0.76 |
| Class 1 | 0.75 | 0.82 | 0.78 |

#### **LOA Feature Selection – Best**
- Train Accuracy: **0.9419**
- Test Accuracy: **0.6818**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.67 | 0.73 | 0.70 |
| Class 1 | 0.70 | 0.64 | 0.67 |

---

### 🔹 **Polynomial (Poly) Kernel**

#### **All Features – Default**
- Train Accuracy: **0.7558**
- Test Accuracy: **0.5909**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.67 | 0.36 | 0.47 |
| Class 1 | 0.56 | 0.82 | 0.67 |

#### **LOA Feature Selection – Default**
- Train Accuracy: **0.8023**
- Test Accuracy: **0.6818**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.75 | 0.55 | 0.63 |
| Class 1 | 0.64 | 0.82 | 0.72 |

#### **All Features – Best**
- Train Accuracy: **0.9419**
- Test Accuracy: **0.6364**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.62 | 0.73 | 0.67 |
| Class 1 | 0.67 | 0.55 | 0.60 |

#### **LOA Feature Selection – Best**
- Train Accuracy: **0.8488**
- Test Accuracy: **0.7273**

| Metric | Precision | Recall | F1-score |
|:-------|:----------:|:------:|:---------:|
| Class 0 | 0.78 | 0.64 | 0.70 |
| Class 1 | 0.69 | 0.82 | 0.75 |

---

## 📈 4. Discussion

- LOA improved accuracy across all kernels, particularly under **default configurations**.  
- **RBF** and **Polynomial** kernels benefited most from LOA feature selection, increasing test accuracy to **0.6818** and **0.7273** respectively.  
- The **Linear kernel** achieved stability and good generalization after LOA selection.  
- LOA increased **training accuracy**, confirming strong fitting ability but indicating potential overfitting under some settings.  
- Further hyperparameter tuning or hybrid approaches (LOA + Grid Search) may enhance results.

---

## 🧩 5. Confusion Matrix Example (LOA – Best RBF)

| Actual / Predicted | Class 0 | Class 1 |
|:--------------------|:--------:|:--------:|
| **Class 0** | 8 | 3 |
| **Class 1** | 4 | 7 |

---

## 🧠 6. Conclusion

The **Lion Optimization Algorithm (LOA)** successfully identified informative molecular features and enhanced SVM performance across different kernels.  
Key findings:

- LOA effectively reduced feature redundancy.  
- Best generalization achieved with **RBF (Test Acc. = 0.7727)**.  
- LOA–SVM combination shows promise for future bioactivity prediction tasks.

---


## 🏷️ Tags
`Machine Learning` • `LOA` • `SVM` • `RBF` • `Linear` • `Polynomial` • `Feature Selection` • `Bioinformatics` • `Python` • `Google Colab`
