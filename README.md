# Electrical Fraud Detection System ⚡️🔍

An AI-powered web application designed to identify electricity usage anomalies and potential fraud using a stacked ensemble machine learning model.

## 📌 Project Overview
Electrical Fraud Detection leverages historical consumption data (current and voltage across three phases) to detect irregularities such as meter tampering or illegal connections. The system uses a **Stacked Ensemble Model** (Random Forest + Gradient Boosting + Meta-Regressor) to ensure high-accuracy predictions.

## 📂 Project Structure
```text
ELECTRICAL FRAUD DETECTION/
├── api/
│   └── main.py          # FastAPI application & web interface
├── data/
│   └── data.csv         # Training/reference datasets
├── models/
│   └── ensemble.pkl     # Trained serialized model
├── src/
│   ├── preprocess.py    # Data cleaning & feature engineering
│   ├── train_models.py  # Model training script
│   └── ensemble.py      # Ensemble logic
├── requirements.txt     # Project dependencies
└── README.md            # Documentation
