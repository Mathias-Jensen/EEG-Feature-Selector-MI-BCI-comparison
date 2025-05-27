# EEG-Feature-Selector-MI-BCI-comparison
EEG Feature Selector for Motor Imagery BCI Comparison
# EEG Feature Selection for Motor Imagery BCI

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
5. **Evaluation** (Accuracy, F1 Score, AUC, confusion matrix, runtime)

## 📊 Results Summary

| Method      | Accuracy | AUC  | Best Channel |
|-------------|----------|------|---------------|
| GA          | 97.22%   | 0.97 | 20            |
| CFS         | 96.22%   | 0.96 | 16            |
| HSIC Lasso  | 96.22%   | 0.96 | 16            |
| Random Forest | 93.67% | 0.93 | 16            |

Data are in corresponding folders.


## 🧪 Requirements

- Python 3.8+
- NumPy, SciPy, scikit-learn, matplotlib, pyHSICLasso, pandas

Install with:

```bash
pip install -r requirements.txt

## 📂 Dataset

The dataset used in this project consists of EEG recordings from motor imagery (MI) tasks — specifically imagined right-hand and foot movements. It includes multi-channel EEG signals sampled at 200 Hz and has been preprocessed and segmented for feature extraction and classification.

You can download the dataset from the link below:

👉 [Download EEG Dataset](https://drive.google.com/file/d/1EVRUUhwPm5-1mrG9DwZycJ91nvWOKYpw/view?usp=sharing)

> **Note:** After downloading, unzip the dataset into the root project directory or update the data paths in your scripts accordingly.
