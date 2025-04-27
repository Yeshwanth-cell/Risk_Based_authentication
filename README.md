# 🛡️ Risk-Based Authentication (RBA) - Freeman Model + Machine Learning

## 📌 Overview
This project implements a **Risk-Based Authentication (RBA)** framework combining behavioral analysis and supervised machine learning.  
We use the **Freeman Model** to assign dynamic risk scores to login attempts and train ML models to predict the likelihood of **Account Takeovers (ATO)**.

## 📊 Dataset
- **Large-scale login event dataset** (~10GB)
- Features include IP address, device info, geolocation, and login timestamps
- Labels indicating whether a login resulted in an account takeover

## 🔍 Methodology

### 1. Freeman Model for Risk Scoring
- Constructed **hash tables** to track user behavior patterns
- Assigned **likelihood-based risk scores** for attributes like IP, Device, and Browser
- Computed **overall risk scores** based on weighted likelihoods

### 2. Machine Learning Classification
- Applied models:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost
- Preprocessing:
  - SMOTE for handling class imbalance
  - Feature engineering from login metadata

### 3. Visualization and Evaluation
- Plotted risk score distributions
- Heatmaps and bar charts of device/country usage
- Evaluated ML models using:
  - Accuracy
  - AUC-ROC
  - F1-Score
  - Confusion Matrix

## ⚙️ Tech Stack
- Python (Pandas, NumPy, Scikit-learn, XGBoost, Imbalanced-learn)
- Matplotlib, Plotly for visualization
- Jupyter Notebook for development and dashboard creation

## 🚀 Results
- Achieved **over 92% AUC** with XGBoost model
- Identified high-risk login patterns using RBA scores
- Built an interactive dashboard to explore risk analysis and model predictions

## 📂 Project Structure
```
rbac/
├── rba_freeman_model.py
├── ml_model_training.py
├── visualization.py
├── data/
│   └── login_dataset.csv
├── notebooks/
│   └── RBA_Analysis.ipynb
├── README.md
└── requirements.txt
```

## 📈 Key Learnings
- Integration of **statistical risk scoring** and **predictive machine learning**
- Importance of **historical behavior tracking** for authentication security
- Handling **class imbalance** and evaluating model performance for rare-event detection

## 🧠 Future Improvements
- Real-time streaming implementation
- Incorporate deep learning (e.g., LSTM) for sequential login pattern detection
- Deploy as a microservice API for live risk scoring
