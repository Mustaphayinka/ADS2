# Breast Cancer Classification Analysis

This repository contains the code and analysis for classifying breast cancer tumors as benign or malignant using the Breast Cancer Wisconsin (Original) dataset from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/15/breast+cancer+wisconsin+original). The project applies Linear Regression and Logistic Regression models to explore and evaluate their performance for binary classification tasks.

---

## Dataset Overview

- **Source**: [Breast Cancer Wisconsin (Original)](https://archive.ics.uci.edu/dataset/15/breast+cancer+wisconsin+original)
- **Number of Instances**: 699
- **Number of Features**: 9 (numerical)
- **Target Variable**: 
  - Class 2: Benign
  - Class 4: Malignant

---

## Project Structure

- `data/`: Contains the dataset (`breast_cancer_wisconsin.xlsx`).
- `notebooks/`: Jupyter Notebook with detailed step-by-step analysis (`Breast_Cancer_Classification.ipynb`).
- `plots/`: Saved figures used in the analysis and report.
- `README.md`: This file.

---

## Data Preprocessing

The following preprocessing steps were performed:
1. **Missing Value Handling**: Missing values in the `Bare_nuclei` column were imputed using the median, ensuring dataset integrity while minimizing outlier impact.
2. **Feature Scaling**: All features were standardized using `StandardScaler` to ensure uniform scaling, as both Linear and Logistic Regression are sensitive to feature magnitudes.
3. **Class Imbalance Handling**: Addressed class imbalance (458 benign vs. 241 malignant) by applying the `class_weight="balanced"` parameter in Logistic Regression training.
4. **Multicollinearity**: The feature `Uniformity_of_cell_shape` was removed during Linear Regression to reduce redundancy and improve interpretability.

---

## Models Implemented

### 1. **Linear Regression**
- Applied as a baseline for comparison.
- **R-squared**: 82.62% - Indicates the proportion of variance explained by the model.
- **Mean Squared Error (MSE)**: 0.1516 - Highlights its limitation in discrete class prediction.
- **Key Limitation**: Continuous predictions make it unsuitable for binary classification tasks.

### 2. **Logistic Regression**
- Designed for binary classification tasks.
- **Accuracy**: 97.14% - Demonstrates strong classification performance.
- **Confusion Matrix**: Minimal misclassifications.
- **Key Features**:
  - `Bare_nuclei`: Most influential predictor of malignancy.
  - `Clump_thickness` and `Uniformity_of_cell_size`: Significant for classification tasks.

---

## Visualizations

1. **Class Distribution**: Highlights the imbalance between benign and malignant cases.
2. **Feature Distributions**: Histograms showcasing variability across features.
3. **Residuals Plot (Linear Regression)**: Reveals scattered residuals, emphasizing the model’s misalignment with binary targets.
4. **ROC-AUC Curve (Logistic Regression)**: Demonstrates the strong discriminatory ability of Logistic Regression.

Saved plots are available in the `plots/` directory.

---

## Key Insights

- **Logistic Regression** proved to be the most effective model for binary classification, achieving a high accuracy of 97.14%.
- Feature importance analysis emphasized `Bare_nuclei` as the most critical predictor, aligning with its biological relevance.
- Linear Regression, while informative for exploring feature relationships, is inadequate for binary classification due to its continuous output nature.

---

## Recommendations

1. **Focus on Key Features**:
   - `Bare_nuclei`, `Clump_thickness`, and `Uniformity_of_cell_size` should be prioritized in diagnostic workflows.
2. **Enhance Diagnostic Models**:
   - Refine Logistic Regression models further to improve recall for malignant cases and reduce false negatives.
3. **Integrate into Medical Diagnostics**:
   - Incorporate Logistic Regression models into tumor classification pipelines for accurate and reliable predictions.

---

## How to Use This Repository

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/breast-cancer-classification.git
