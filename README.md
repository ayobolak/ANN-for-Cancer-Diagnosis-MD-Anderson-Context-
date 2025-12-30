# ANN-for-Cancer-Diagnosis-MD-Anderson-Context-
ANN for Cancer Diagnosis (MD Anderson Context)
# ANN for Cancer Diagnosis (MD Anderson Context) — TensorFlow

## Project Overview
This project implements an Artificial Neural Network (ANN) using TensorFlow to diagnose cancer (malignant vs benign) based on imaging-derived diagnostic features. A publicly available Kaggle dataset is used and assumed to be provided by MD Anderson Cancer Institute for this exercise.

The objective is to demonstrate how neural networks can support radiologists by learning complex, non-linear relationships in diagnostic data and improving decision support over time.

---

## Dataset
- **Source:** Kaggle – Breast Cancer Wisconsin (Diagnostic) Dataset
- **File:** data.csv
- **Target Variable:** diagnosis  
  - M = Malignant  
  - B = Benign  

The dataset contains numerical features computed from digitized images of breast mass samples, making it appropriate for cancer diagnosis modeling.

---

## Methodology

### Data Preprocessing
- Removed non-informative identifier columns and empty fields.
- Encoded the diagnosis label into binary numeric format.
- Applied a stratified train/test split to preserve class balance.
- Standardized features using StandardScaler (fit on training data only).

### Model Architecture
- Two hidden dense layers (32 and 16 neurons) with ReLU activation.
- Dropout regularization to reduce overfitting.
- Sigmoid output layer for binary classification.
- Binary cross-entropy loss with Adam optimizer.

### Training
- Trained using early stopping on validation loss to prevent over-training.
- Best model weights were restored automatically.

---

## Evaluation Results
Test set performance:

- **Accuracy:** 98.25%
- **Precision:** 100%
- **Recall:** 95.24%
- **F1-Score:** 97.56%

Confusion Matrix:
- True Negatives: 72
- False Positives: 0
- False Negatives: 2
- True Positives: 40

Threshold tuning further improved recall to 97.62% while maintaining perfect precision, demonstrating a safer clinical trade-off for cancer screening.

---

## Clinical Relevance
This model is intended as a decision-support tool to assist radiologists by prioritizing potentially malignant cases for review. It does not replace clinical judgment but enhances diagnostic efficiency and sensitivity.

---

## Repository Structure
