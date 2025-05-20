# EEG-Feature-Selector-MI-BCI-comparison
EEG Feature Selector for Motor Imagery BCI Comparison

This repository presents a comparative evaluation of four feature selection techniques for EEG-based Brain–Computer Interface (BCI) classification, using motor imagery (MI) data of right hand (RHD) and right foot (RFT) movements.

## 📋 Overview

The goal of this project is to identify the most effective feature selection strategy for improving classification performance in EEG motor imagery tasks, while balancing computational cost and interpretability. The selected features are evaluated using a Support Vector Machine (SVM) classifier, with performance measured across multiple metrics.

## 🧠 Feature Selection Methods Compared

- 🧬 **Genetic Algorithm (GA)** — population-based wrapper method optimizing feature subsets
- 🌲 **Random Forest (RF)** — wrapper using feature importance from ensemble decision trees
- 🔗 **Correlation-based Feature Selection (CFS)** — filter based on class correlation vs. redundancy
- 🧪 **HSIC Lasso** — kernel-based filter using Hilbert-Schmidt Independence Criterion

## 🧪 Dataset

- 118-channel EEG recordings
- 500,000 samples of imagined **right hand (RHD)** movement
- 400,000 samples of imagined **right foot (RFT)** movement
- Sampling rate: 200 Hz

## ⚙️ Pipeline

1. **Signal Preprocessing** (Notch + Bandpass filtering)
2. **Feature Extraction** (27 time, frequency, statistical & entropy features)
3. **Feature Selection** (Max 2 features per method)
4. **Classification** (SVM with RBF kernel, 5-fold cross-validation)
5. **Evaluation** (Accuracy, F1 Score, AUC, confusion matrix)

## 📊 Results Summary

| Method      | Accuracy | AUC  | Best Channel |
|-------------|----------|------|---------------|
| GA          | 97.22%   | 0.97 | 20            |
| CFS         | 96.22%   | 0.96 | 16            |
| HSIC Lasso  | 96.22%   | 0.96 | 16            |
| Random Forest | 93.67% | 0.93 | 16            |

See folders for detailed ROC curves, performance tables, and decision boundaries.


## 🧪 Requirements

- Python 3.8+
- NumPy, SciPy, scikit-learn, matplotlib, pyHSICLasso, pandas

Install with:

```bash
pip install -r requirements.txt

