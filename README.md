# [FinTech] Real-Time Fraud Detection Engine

## 🎯 Business Problem
Financial institutions lose billions annually to fraudulent transactions. The goal of this project was to build a low-latency system capable of flagging high-risk transactions (e.g., high amounts at unusual hours or locations) in real-time while providing clear explanations for why a transaction was blocked.

## 📊 Key Results
- **Model Performance:** Achieved a balanced classification approach to minimize false negatives (missed fraud).
- **Explainability:** Integrated **SHAP** to provide "Reason Codes" for every flagged transaction, ensuring regulatory compliance.
- **Latency:** Designed an API endpoint capable of delivering decisions in under 50ms.

## 🛠 Methodology
1. **Data Engineering:** Generated a synthetic dataset of 20,000 transactions with engineered fraud patterns (e.g., "The 3 AM International Spike").
2. **Predictive Modeling:** Trained a **Random Forest Classifier** with class-weight balancing to handle the extreme data imbalance typical in fraud detection.
3. **Production API:** Wrapped the model in a **FastAPI** web server to simulate a live banking environment.
4. **Explainable AI (XAI):** Implemented a SHAP Explainer to decompose model predictions into human-readable feature impacts.

## 📂 Project Structure
- `data/`: Synthetic transaction logs.
- `models/`: Serialized Random Forest model (`.pkl`).
- `app/`: FastAPI production script.
- `visuals/`: SHAP force plots and global feature importance charts.

## 📈 Visuals
The `/visuals` folder contains:
- `global_fraud_importance.png`: Shows that **Transaction Amount** and **Hour of Day** are the strongest predictors.
- `fraud_explanation_sample.png`: A SHAP force plot explaining a specific "Flagged" decision.
