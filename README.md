# 💳 Loan Default Prediction System

> An end-to-end machine learning pipeline that classifies loan applicants as **High Risk** or **Low Risk**, deployed via Flask and Streamlit with an integrated chatbot for interactive risk scoring.

---

## 📌 Problem Statement

Lending companies face a critical challenge when assessing creditworthiness — especially for applicants with limited credit history. Approving high-risk borrowers leads to financial losses, while rejecting reliable clients means missed opportunities. This project builds a reliable AI-driven tool to minimize defaults while ensuring fair access for genuine borrowers.

---

## 📊 Dataset

- **Size:** 159 features across two merged tables:
  - **Application Data** (122 features): Demographics, employment, existing debts, loan details
  - **Previous Application Data** (37 features): Past loan history, repayment behavior, credit outcomes

---

## 🔧 Project Pipeline

### 1. Data Cleaning & Preprocessing
- Removed duplicates, inconsistent entries, and invalid records
- Standardized data formats across both tables
- Handled missing values via appropriate imputation techniques

### 2. Outlier Handling
- Detected and treated extreme values using statistical methods
- Ensured data stability and reliable model performance

### 3. Exploratory Data Analysis (EDA)
- Univariate & bivariate analysis on key financial features
- Correlation heatmaps to detect relationships between features
- Categorical feature exploration (education, occupation, housing type)
- Outlier behavior checks using boxplots and distribution metrics

### 4. Feature Engineering
- Created domain-specific features: debt-to-income ratio, credit utilization, approval/rejection ratios
- Transformed variables to improve model signal

### 5. Model Development & Evaluation

| Model | Train Accuracy | Test Accuracy | ROC-AUC |
|---|---|---|---|
| CatBoost | — | 81% | 96.7% |
| Random Forest | 99% | ~94% | — |
| **LightGBM** ✅ | **95%** | **94.5%** | **97%** |

**Best Model: LightGBM**
- Precision = 1.00 for defaulters (zero false positives)
- Recall = 1.00 for non-defaulters (zero false negatives)
- Best balance between identifying risky and safe applicants

---

## 🚀 Deployment

### Flask Web Application
- Multi-step form for applicant information and previous loan history
- Real-time risk prediction with High/Low risk classification
- Integrated chatbot for interactive guidance and Q&A

### Streamlit Application
- Lightweight interface for quick testing and prototyping
- Same prediction pipeline with chatbot integration

---

## 🤖 Chatbot
- Handles user questions about loan applications
- Processes applicant input and returns risk scoring
- Integrated into both Flask and Streamlit deployments

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| ML Libraries | Scikit-learn, LightGBM, CatBoost |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Deployment | Flask, Streamlit |
| Version Control | Git, GitHub |

---

## 👥 Team Contributions

| Member | Contributions |
|---|---|
| Mohammed Yasser Ismael | Data cleaning, LightGBM model, feature selection |
| Abdelrahman Hassan Shaaban | EDA, Streamlit & Flask deployment, model deployment |
| Noureldin Mohamed Amin | Outlier handling, chatbot development, project documentation |
| Mohamed Ayman Afifi | Feature engineering, Random Forest model |
| Mark Hany Adel | EDA (previous dataset), CatBoost model |

---

## 📁 Project Structure

```
loan-default-prediction/
├── notebooks/
│   ├── 1_DataSummary.ipynb
│   ├── 2_Feature_Enginering.ipynb
│   ├── 4_HandlingOutliers.ipynb
│   ├── 5_EDA_application_dataset.ipynb
│   └── 6_EDAPrevious.ipynb
├── flask_app/
│   └── app.py
├── streamlit_app/
│   └── streamlit_app.py
├── models/
│   ├── randomforest_model.pkl
│   ├── catboost_model.pkl
│   └── lightgbm_model.pkl
└── README.md
```

---

## ⚙️ Setup & Installation

```bash
# Clone the repository
git clone https://github.com/your-username/loan-default-prediction.git
cd loan-default

# Install dependencies
pip install -r requirements.txt

# Run Flask app
python flask_app/app.py

# Or run Streamlit app
streamlit run streamlit_app/streamlit_app.py
```

---

## 📄 License

This project was developed as a graduation project for the **Digital Egypt Pioneers Initiative (DEPI)** — AI & Data Science Track, December 2025.