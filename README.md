# Telecoms  – Customer Cease Prediction

##  Project Objective

UK Telecoms LTD aims to prioritise customer retention efforts by identifying customers most likely to place a cease (leave the company).

The goal of this project is to:

- Predict probability of cease placement
- Rank customers by risk score
- Enable targeted retention campaigns
- Optimise call centre resource allocation

This solution was developed in Python using a structured end-to-end machine learning approach.

---

##  Business Problem

The business cannot contact all customers due to limited retention resources.

Therefore, the objective is to:

> Identify and prioritise high-risk customers to maximise retention ROI.

The output of this project is a customer-level risk score that enables data-driven retention decisions.

---

## Data Sources

Four synthetic datasets were provided:

### 1️ Customer Information
- Contract status
- Direct debit cancellations
- Out-of-contract days
- Technology type
- Sales channel
- Package details
- Tenure

### 2️ Cease Data
- Cease placed date
- Cease completed date
- Reason for leaving

### 3️ Call Centre Data
- Call type (Loyalty, CS&B)
- Talk time (seconds)
- Hold time (seconds)
- Call frequency

### 4️ Usage Data
- Daily download usage (MB)
- Daily upload usage (MB)

All datasets were joined using:
```
unique_customer_identifier
```

---

## End-to-End Approach

```
Raw Data (Customer + Usage + Calls + Cease)
                    ↓
Data Cleaning & Integration (DuckDB + Pandas)
                    ↓
Feature Engineering
                    ↓
Cease Label Creation
                    ↓
Train/Test Split
                    ↓
LightGBM Model Training
                    ↓
Model Evaluation
                    ↓
Risk Scoring & Business Recommendations
```

---

## ⚙️ Technical Stack

- Python
- DuckDB
- Pandas
- NumPy
- LightGBM
- Scikit-learn
- SHAP
- Matplotlib
- Seaborn

---

## 🛠 Feature Engineering

Feature engineering focused on behavioural risk signals aligned with real-world churn patterns.

### Contract & Risk Features
- Out-of-contract days
- Contract status flags
- Direct debit cancellations (recent + historical)

### Call Behaviour Features
- Total call frequency
- Loyalty team call count
- Average talk time
- Total hold time
- Recent call activity

### Usage Behaviour Features
- Total download/upload usage
- Average daily usage
- Usage trends
- Speed mismatch (expected vs actual)

### Customer Lifecycle Features
- Tenure
- Technology type encoding
- Sales channel encoding

These features capture patterns that typically precede cease placement.

---

## 🤖 Model Selection

Model Used: **LightGBM Classifier**


## 📊 Model Performance

| Metric | Score |
|--------|--------|
| ROC-AUC | 0.97 |
| Accuracy | 92% |
| Precision (Cease) | 96% |
| Recall (Cease) | 91% |

### Interpretation

- Strong discrimination ability (ROC-AUC 0.97)
- High recall ensures most high-risk customers are identified
- High precision ensures retention calls are well targeted

This model provides reliable risk ranking for business prioritisation.

---


##  Business Recommendation

Instead of calling all customers:

1. Score all customers using the trained model
2. Rank customers by predicted cease probability
3. Target top 15–20% highest-risk customers

---

##  Deliverables Included


- Python notebooks
- PowerPoint presentation (10-minute summary)

---

##  Conclusion

This project delivers a robust, interpretable, and business-focused cease prediction model that enables UK Telecoms LTD to:

- Proactively identify high-risk customers  
- Prioritise retention resources effectively  
- Improve customer lifetime value  

---
