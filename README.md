# SMO SVM + Kernel Extensions for Breast Cancer Classification

_An in-depth implementation of the Sequential Minimal Optimization (SMO) algorithm with kernel support for supervised classification on medical datasets._

## Table of Contents

1. [Description](#description)  
2. [Key Features](#key-features)  
3. [Tech Stack](#tech-stack)  
4. [Installation](#installation)  
5. [Datasets](#datasets)  
6. [Usage](#usage)  
7. [Project Structure](#project-structure)  
8. [Configuration](#configuration)

---

## Description

This project re-derives and implements the SMO algorithm to solve the dual form of the soft-margin SVM, supporting linear, RBF, and polynomial kernels. We benchmark our solver against scikit-learn’s SVC on the UCI Breast Cancer Wisconsin and Pima Indians Diabetes datasets, providing transparency and auditability for high-stakes medical classification tasks.

## Key Features

- **Custom SMO Solver**: Sequential Minimal Optimization implementation for dual SVM.  
- **Kernel Support**: Linear, Gaussian RBF, and polynomial kernels with hyperparameter tuning.  
- **Benchmarking**: Comparison with scikit-learn's SVC on accuracy, training time, and support-vector analysis.  
- **Diagnostics**: Margin width, convergence tracking, and PCA-based dimensionality study.  
- **Reproducibility**: 5-fold cross-validation and explicit GridSearchCV routine.  

## Tech Stack

- **Language:** Python 3.8+  
- **Notebook:** Jupyter Notebook (`Group_project_v2.ipynb`)  
- **Libraries:** numpy, pandas, scikit-learn, matplotlib, seaborn  

## Installation

```bash
git clone https://github.com/your-username/mgsc676-smo-svm.git
cd mgsc676-smo-svm
python -m venv venv
source venv/bin/activate  # macOS/Linux
venv\Scripts\activate   # Windows
pip install -r requirements.txt
```

## Datasets

- **Breast Cancer Wisconsin (Diagnostic)**: 569 samples, 30 features (malignant vs. benign).  
- **Pima Indians Diabetes**: 768 samples, 8 features.  

Place raw CSV files in the `data/` directory before running analysis.

## Usage

1. Launch Jupyter:  
   ```bash
   jupyter notebook Group_project_v2.ipynb
   ```  
2. Run cells in order:  
   - SMO implementation and kernel functions  
   - Cross-validation and hyperparameter search  
   - Benchmarking and diagnostic plots  
   - PCA and support-vector analysis  
   - External dataset validation  

## Project Structure

```
mgsc676-smo-svm/
├── README_MGSC676.md        # This file
├── requirements.txt         # Dependencies
├── data/                    # Raw datasets
│   ├── breast_cancer.csv
│   └── pima_diabetes.csv
├── Group_project_v2.ipynb   # Analysis notebook
└── figures/                 # Output charts
    ├── convergence.png
    └── pca_diagnostics.png
```

## Configuration

- **C (Regularization)**: Adjust soft-margin parameter for different kernels.  
- **Kernel Parameters**: Sigma for RBF, degree for polynomial kernels.  
- **tol**: Convergence tolerance for SMO loop.  
- **random_state**: Seed for reproducible splits.  
