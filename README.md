# 💳 Intelligent Credit Card Fraud Detection

An end-to-end Machine Learning project that detects fraudulent credit card transactions using Random Forest and handles highly imbalanced financial data with SMOTE.

---

## 📌 Project Overview

With the rapid growth of digital payments, credit card fraud has become a major financial threat. Fraudulent transactions are:

- Rare (Highly imbalanced dataset)
- Complex and evolving
- Difficult to detect manually

This project builds an intelligent fraud detection system using machine learning techniques to accurately identify fraudulent transactions while minimizing false positives.

---

## 📊 Dataset Information

- Dataset: Credit Card Transactions Dataset
- Total Records Used After Cleaning: 23,770
- Total Features: 30
  - V1–V28 (PCA-transformed features)
  - Time
  - Amount
- Target Variable:
  - 0 → Genuine Transaction
  - 1 → Fraudulent Transaction

⚠️ The dataset is highly imbalanced.

---

## 🛠️ Technologies Used

- Python 3.x
- Google Colab / Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)

---

## 🔄 Project Workflow

### 1️⃣ Import Required Libraries
Used essential ML and visualization libraries along with SMOTE for balancing.

### 2️⃣ Load Dataset
```python
df = pd.read_csv('creditcard.csv')
```

### 3️⃣ Data Cleaning
- Checked missing values
- Removed duplicate records
- Dropped rows with missing target values

After removing duplicates:
```
(23770, 31)
```

---

### 4️⃣ Feature Scaling
Standardized `Amount` and `Time` features using `StandardScaler`.

---

### 5️⃣ Train-Test Split

- 80% Training Data
- 20% Testing Data
- Stratified split to maintain class balance

```
Training shape: (19015, 30)
Testing shape: (4754, 30)
```

---

### 6️⃣ Model Training

Used **Random Forest Classifier** with:

- 200 estimators
- `class_weight="balanced"`
- `random_state=42`

```python
RandomForestClassifier(n_estimators=200, class_weight="balanced")
```

---

## 📈 Model Performance (Without SMOTE)

| Metric        | Score |
|--------------|--------|
| Recall       | 0.83 |
| Precision    | 0.94 |
| F1-Score     | 0.88 |
| ROC-AUC      | 0.97 |

### Classification Report

- Fraud Recall: **83%**
- Very high precision
- Strong ROC-AUC performance

---

## 📊 ROC Curve

Model achieved a strong ROC-AUC score of:

```
0.9711
```

Indicating excellent discrimination capability between fraud and genuine transactions.

---

## 📊 Confusion Matrix

- Very few false negatives
- Minimal false positives
- High overall accuracy

---

## 🔥 Model Improvement Using SMOTE

To handle class imbalance, SMOTE (Synthetic Minority Oversampling Technique) was applied.

### 📈 Performance With SMOTE

| Metric        | Score |
|--------------|--------|
| Recall       | 0.94 |
| ROC-AUC      | 0.97 |

✅ Fraud detection recall improved from **83% → 94%**

This significantly improves fraud detection capability.

---

## 🎯 Key Achievements

- Successfully handled highly imbalanced data
- Achieved 94% recall on fraud cases using SMOTE
- ROC-AUC close to 0.97
- Built complete ML pipeline:
  - Preprocessing
  - Scaling
  - Model training
  - Evaluation
  - Visualization

---

## 🖥️ System Requirements

### Hardware:
- Intel i5 / Ryzen 5 or higher
- Minimum 8GB RAM

### Software:
- Python 3.x
- Jupyter Notebook / Google Colab

Install dependencies:
```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
```

---

## ▶️ How to Run

1. Clone the repository:
```bash
git clone https://github.com/your-username/intelligent-credit-card-fraud-detection.git
```
2. Open the notebook in Jupyter or Colab and run all cells.

---

## 🚀 Future Scope

- Deploy as a real-time fraud detection API
- Integrate with banking systems
- Use Deep Learning (ANN, LSTM)
- Implement anomaly detection models
- Build web-based fraud monitoring dashboard

---


## 📌 Conclusion

This project demonstrates that machine learning combined with proper preprocessing and imbalance handling techniques can effectively detect fraudulent credit card transactions with high recall and reliability.

The system significantly enhances financial transaction security and reduces fraud risk.

---

⭐ If you found this project useful, consider giving it a star!
