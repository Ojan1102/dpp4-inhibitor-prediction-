# 🧠 Lion Optimization Algorithm (LOA) – SVM with RBF Kernel

This project implements the **Lion Optimization Algorithm (LOA)** for feature selection in a **Support Vector Machine (SVM)** classifier using the **Radial Basis Function (RBF)** kernel.  
The objective is to optimize SVM performance by selecting the most informative features from molecular descriptor data.

---

## ⚙️ 1. Method Overview

- **Algorithm:** Lion Optimization Algorithm (LOA)  
- **Model:** Support Vector Machine (SVM)  
- **Kernel:** Radial Basis Function (RBF)  
- **Objective:** Feature selection and performance enhancement  
- **Dataset:** Molecular descriptors with binary classification labels (e.g., IC₅₀ thresholded activity)

LOA is a nature-inspired metaheuristic that mimics the **social behavior of lions** in the wild, consisting of:
- Pride and Nomad populations  
- Mating, hunting, and territorial defense behaviors  
- Exploration–exploitation balance  

The algorithm selects a subset of features that maximizes model accuracy while reducing redundancy.

---

## 🧩 2. Experimental Setup

Four configurations were tested:

| Model | Feature Selection | Kernel | Parameters | Description |
|--------|------------------|---------|-------------|--------------|
| A | None (All Features) | RBF | Default | Baseline model |
| B | LOA | RBF | Default | LOA-selected features using default hyperparameters |
| C | None (All Features) | RBF | Best | Tuned SVM parameters (grid search) |
| D | LOA | RBF | Best | LOA-selected features + tuned parameters |

---

## 📊 3. Results Summary

### **A. All Features – Default (RBF)**  
- **Train Accuracy:** 0.7326  
- **Test Accuracy:** 0.6364  

| Metric | Precision | Recall | F1-score |
|---------|------------|---------|----------|
| Class 0 | 1.00 | 0.27 | 0.43 |
| Class 1 | 0.58 | 1.00 | 0.73 |
| **Macro Avg** | 0.79 | 0.64 | 0.58 |

---

### **B. LOA Feature Selection – Default (RBF)**  
- **Train Accuracy:** 0.7791  
- **Test Accuracy:** 0.6818  

| Metric | Precision | Recall | F1-score |
|---------|------------|---------|----------|
| Class 0 | 0.83 | 0.45 | 0.59 |
| Class 1 | 0.62 | 0.91 | 0.74 |
| **Macro Avg** | 0.73 | 0.68 | 0.66 |

---

### **C. All Features – Best (RBF)**  
- **Train Accuracy:** 0.8605  
- **Test Accuracy:** 0.7727  

| Metric | Precision | Recall | F1-score |
|---------|------------|---------|----------|
| Class 0 | 0.80 | 0.73 | 0.76 |
| Class 1 | 0.75 | 0.82 | 0.78 |
| **Macro Avg** | 0.78 | 0.77 | 0.77 |

---

### **D. LOA Feature Selection – Best (RBF)**  
- **Train Accuracy:** 0.9419  
- **Test Accuracy:** 0.6818  

| Metric | Precision | Recall | F1-score |
|---------|------------|---------|----------|
| Class 0 | 0.67 | 0.73 | 0.70 |
| Class 1 | 0.70 | 0.64 | 0.67 |
| **Macro Avg** | 0.68 | 0.68 | 0.68 |

---

## 📈 4. Discussion

- LOA feature selection improved test accuracy **from 0.6364 → 0.6818** under default parameters.  
- After hyperparameter tuning (Best-RBF), the **All Features** model achieved a higher test accuracy (**0.7727**) than LOA (**0.6818**).  
- LOA achieved **higher training accuracy (0.9419)**, showing strong fitting capability.  
- These results indicate that LOA effectively reduces feature redundancy but may require further tuning to improve generalization.

---

## 🧩 5. Confusion Matrix (Example for LOA–Best RBF)

| Actual / Predicted | Class 0 | Class 1 |
|--------------------|----------|----------|
| **Class 0** | 8 | 3 |
| **Class 1** | 4 | 7 |

---

## 🧠 6. Conclusion

The Lion Optimization Algorithm successfully selected informative features and improved baseline performance.  
Future improvements could involve:
- Hybrid LOA–SVM tuning (simultaneous feature and parameter optimization)  
- Comparison with other metaheuristics (PSO, GA, ACO)  
- Application to larger or more diverse molecular datasets  

---

## 📚 Reference

This implementation and results are part of a research study on **bioactivity prediction of DPP-4 inhibitors** using **LOA–SVM (RBF Kernel)**.
