# Electrical Fraud Detection System 

An AI-powered web application designed to identify electricity usage anomalies and potential fraud using a stacked ensemble machine learning model.

##  Project Overview
Electrical Fraud Detection leverages historical consumption data (current and voltage across three phases) to detect irregularities such as meter tampering or illegal connections. The system uses a **Stacked Ensemble Model** (Random Forest + Gradient Boosting + Meta-Regressor) to ensure high-accuracy predictions.
##  Key Features

* **Stacked Ensemble Learning:** Utilizes a multi-layer architecture (Random Forest and Gradient Boosting) to minimize bias and variance, ensuring robust detection.
* **Real-time Prediction Engine:** A lightweight web interface allows for manual data entry with sub-second inference results.
* **3-Phase Power Analysis:** Specifically monitors current ($I_a, I_b, I_c$) and voltage ($V_a, V_b, V_c$) fluctuations to identify phase-specific tampering.
* **Confidence Scoring:** Each prediction is accompanied by a probability score, allowing utility operators to prioritize high-risk anomalies.

---

##  Data & Input Features

The model processes **6 core electrical parameters** to determine the likelihood of fraud:

| Parameter | Description | Unit |
| :--- | :--- | :--- |
| **Ia, Ib, Ic** | Current values for Phases A, B, and C | Amperes (A) |
| **Va, Vb, Vc** | Voltage values for Phases A, B, and C | Volts (V) |

---

##  Technology Stack

### **Backend & API**
* **FastAPI:** High-performance web framework for building the prediction points.
* **Uvicorn:** Lightning-fast ASGI server implementation for hosting the application.

### **Machine Learning & Data**
* **Scikit-learn:** Powering the Random Forest, Gradient Boosting, and Logistic Regression Meta-model.
* **Pandas & NumPy:** Used for high-speed data manipulation and numerical processing.
* **Joblib:** Efficient serialization for saving and loading the trained ensemble models.

### **Frontend**
* **HTML5 & CSS3:** Modern, responsive UI embedded directly within FastAPI responses for a seamless user experience without external dependencies.
 ---
## Installation and run
- pip install -r requirements.txt
- python src/train_models.py
- uvicorn api.main:app --reload
  
  ---
##  Project Structure
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
