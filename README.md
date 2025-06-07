# 🏦 Predicting SBA Loan Defaults with Machine Learning

A deep dive into SBA 7(a) loan data using machine learning to predict loan defaults and uncover insights that support smarter small business lending decisions.

---

## 🌟 Abstract

This project analyzes U.S. Small Business Administration (SBA) loan data to predict whether a loan will be **charged off** or **paid in full**. We use models such as **Logistic Regression**, **Random Forest**, and **XGBoost** to identify key drivers of default risk based on structured loan attributes.

**Key finding**: Loan **term** and **amount disbursed** are the strongest predictors of default, and the **XGBoost model** achieved the highest predictive performance with over **90% recall**.

---

## 👨‍💼 Motivation

Small businesses are the backbone of the U.S. economy. However, providing capital to small businesses carries inherent risk. This project helps:

- Lenders better **predict default risk** before approval
- Policymakers optimize **loan program design**
- Entrepreneurs access **data-driven financing opportunities**

---

## 🧰 Dataset

- 📁 **File**: `SBAcase.11.13.17.csv`
- 🔢 **Rows**: ~2,100 loans
- 🏷️ **Columns used**:

| Feature             | Description                              |
|---------------------|------------------------------------------|
| `DisbursementGross` | Amount of loan disbursed                 |
| `Term`              | Duration of the loan in months           |
| `NoEmp`             | Number of employees                      |
| `NewExist`          | Whether business is new or existing      |
| `UrbanRural`        | Business location type                   |
| `State`             | US state of borrower                     |
| `MIS_Status`        | Loan status (`Paid in Full` / `CHGOFF`)  |

---

## 🔄 Data Preprocessing

Steps taken:

1. ✅ Dropped missing targets (`MIS_Status`)
2. 🧠 Created binary target:  
   - `1` = Charged Off  
   - `0` = Paid in Full
3. 🧹 Dropped rows with missing values in key features
4. 🔁 Encoded categorical features (`State`, `UrbanRural`, `NewExist`) using `LabelEncoder`

---

## 🔬 Methodology

We compared 3 models using train-test splits and evaluated them with a focus on **default detection**:

| Model              | Accuracy | Recall (Default) | Precision (Default) | ROC-AUC |
|--------------------|----------|------------------|----------------------|---------|
| Logistic Regression | 65%      | 1%               | 100%                 | 0.87    |
| Random Forest       | 90%      | 86%              | 86%                  | 0.95    |
| XGBoost             | 92%      | 90%              | 88%                  | 0.96    |

✅ **XGBoost** proved best for real-world use due to high **recall** and **overall performance**.

---

## 📊 Insights & Visualizations

### 📈 Default by Loan Term

- Loans with terms **> 36 months** had a significantly higher default rate.
- Short-term loans were safer.

### 💰 Loan Amount Distribution

- Most loans were **< $150K**
- Larger loans showed slightly higher default rates

### 🎯 Feature Importance (Random Forest)

- **1. Term**: Most predictive
- **2. DisbursementGross**: Strong influence
- **3. NoEmp / State**: Minimal impact

---

## ⚠️ Challenges

- **Class Imbalance**: Only ~32% of loans were defaults → handled with evaluation metrics like recall, F1
- **Limited Features**: No credit scores, revenues, or financial ratios
- **Overfitting**: Controlled with hyperparameter tuning and depth limits on trees

---

## 🌍 Conclusion

✅ Machine learning models — especially **XGBoost** — can reliably identify SBA loan default risks.  
This opens doors to better risk assessment, tailored financing, and smarter public lending policies.

---

## 🚀 Future Work

- Use borrower-level data: credit scores, revenue, payment history
- Incorporate macroeconomic features like **recession windows**
- Deploy a **risk prediction dashboard** for underwriters or loan officers

---

## 🧠 How to Run

1. Clone this repository
2. Upload `SBAcase.11.13.17.csv` (due to size, not stored here)
3. Run the notebook: `SBA Loan Default Prediction.ipynb`
4. Follow along step-by-step: preprocessing → modeling → evaluation

---

## 👨‍💻 Author

**Hunter** ([@HunterBytes](https://github.com/HunterBytes))  
Golden retriever energy meets fintech + machine learning. Always learning, always building.

---

> “In God we trust. All others must bring data.” — *W. Edwards Deming*
