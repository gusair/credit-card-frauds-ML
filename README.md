# 💳 Credit Card Fraud Detection with Machine Learning

This project dives into one of the most damaging modern cybercrimes: **credit card fraud**. Using a real dataset of credit card transactions from European cardholders, we explore how machine learning can help detect fraudulent activity and protect users from financial harm.

---

## 📂 Dataset

- Source: [Kaggle - Credit Card Fraud Detection](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- Total transactions: **284,807**
- Fraudulent cases: **492** (about 0.17% of the data)
- Features: 30 anonymized variables (via PCA), plus `Time`, `Amount`, and `Class` (target)

---

## 🎯 Project Goals

- Understand the nature of fraudulent transactions
- Visualize patterns that separate fraud from legitimate transactions
- Handle class imbalance
- Train a machine learning model to predict fraud
- Evaluate model performance with proper metrics

---

## 🔍 Key Steps

### 🧼 1. Data Cleaning & Exploration

- No missing data found (`df.isnull().sum().max()` = 0)
- Transactions include PCA-transformed features
- `Time` and `Amount` were **standardized**
- Fraud cases make up only **0.17%** of the data — clear imbalance

### 📊 2. Exploratory Analysis

- Boxplots and KDE plots revealed different distributions for fraud vs. non-fraud
- Fraudulent transactions typically have **smaller amounts**
- Time did not show a meaningful pattern in terms of fraud
- Correlation matrix explored both before and after balancing

### 🧪 3. Data Preparation

- Used `StandardScaler()` to normalize `Time` and `Amount`
- Split dataset into **training and test sets**, preserving class balance with `stratify=True`
- Applied **Random Under Sampling** to create a balanced training set

---

## 🧠 4. Model Building

- **Model used**: Logistic Regression
- Trained on the undersampled dataset
- Predictions made on the original test set (not undersampled)

### 🧾 Evaluation Results

| Metric     | Score   |
|------------|---------|
| Accuracy   | 0.9767  |
| Precision (Fraud) | 0.0623  |
| Recall (Fraud)    | 0.8857  |
| F1 Score (Fraud)  | 0.1165  |
| AUC       | 0.9313  |

Although precision was low, the model achieved **very high recall**, which is critical for fraud detection where **catching fraud** is more important than avoiding false alarms.

---

## 🧰 Tools & Libraries

- Python
- Pandas & NumPy
- Scikit-learn
- Imbalanced-learn (`RandomUnderSampler`)
- Seaborn & Matplotlib

---

## 📌 Final Thoughts

This project shows how machine learning can support financial institutions in identifying fraud. It also highlights the challenges of working with imbalanced datasets, and why proper metrics like **recall** and **AUC** are more meaningful than just accuracy in these cases.

---

## ✍️ Author

Project by Augusto de Jesus  
Built as part of a hands-on learning path in Machine Learning, with a focus on cybersecurity and fraud detection.

---

## 📎 License

This project is for educational and non-commercial use only.
