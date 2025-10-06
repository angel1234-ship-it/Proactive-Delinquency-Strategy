# Proactive Delinquency Strategy: Uncovering the 'Why' to Prevent Loss.
## 🚀 Project Context & Source
This project was developed using a dataset provided through the TATA GenAI Powered Data Analytics Job Simulation program (hosted on the Forage platform).

The goal of the task was to demonstrate how the company can refine its delinquency risk model and improve its intervention strategies by identifying and mitigating hidden, non-linear risk within a customer portfolio.

## 💡 Project Overview
This project focuses on processing raw financial data to identify and model non-linear risk triggers that lead to customer delinquency. The objective was to move beyond the limitations of simple linear models to build a robust, explainable foundation for a proactive loss prevention strategy.

Key Insight: The true risk is non-linear, manifesting as a sharp "cliff-edge" delinquency spike at a specific behavioral threshold.

## 🛠️ Data Cleaning & Feature Engineering
### 1. Data Cleaning
Missing Value Handling:Dropped two records with missing values in credit_score.

Imputed missing values in income and loan_balance using the median to minimize outlier distortion.

Text Standardization: Corrected inconsistent categorical entries (e.g., standardizing 'EMP' to 'Employed').

### 2. Custom Feature Engineering
Total Recent Misses (TRM): Converted categorical repayment records (Month1 through Month6) into numerical scores (e.g., 'on-time' →0) and summed them. This feature was specifically engineered to capture non-linear, time-based risk.

Stability Metric: Calculated the Tenure_to_Age Ratio (tenure_account / age) to create a standardized measure of customer stability.

Top 10 Risk Factors: Identified the most influential features via correlation/association analysis to validate feature selection.

## 🔍 Key Analytical Findings
Finding	Visualization	Strategic Takeaway
The Core Risk Trigger	TRM Risk Threshold Bar Chart	Risk is non-linear. The delinquency rate spikes to 36% at TRM=10, identifying the critical moment for intervention (the 'When').
Linear vs. Non-Linear	Top 10 Risk Factors Chart	Linear correlation was misleading (TRM ranked low). This justified the transition to non-linear analysis.
High-Risk Segment	Segmentation Scatter Plot	The highest-risk customers are defined by the Low Capacity (Income) & Low Stability (Tenure) profile. This is the 'Who' to target.

## 💻 Modeling & Deployment Strategy
Baseline Modeling
Model: Implemented Logistic Regression (LR) as a transparent, auditable baseline.

Finding: The LR model achieved moderate performance, confirming the limitation of linear models in capturing the non-linear TRM risk.

Final Deployment Strategy
A strategic Dual-Model System is proposed to balance trade-offs:

XGBoost/Neural Network: Deployed for Maximum Predictive Accuracy (to detect the TRM spike).

Logistic Regression: Retained for Regulatory Compliance, generating transparent reason codes for collections.

## 🛠️ Tech Stack
Analysis & Modeling: Python (Pandas, NumPy, Scikit-learn)

Visualization: Power BI

Advanced Modeling: XGBoost (Planned Next Step)

## 🖼️ Final Dashboard Snapshot

(https://github.com/angel1234-ship-it/Proactive-Delinquency-Strategy/blob/main/Riskanalysis.pdf)

![Proactive Delinquency Strategy Dashboard](https://github.com/angel1234-ship-it/Proactive-Delinquency-Strategy/blob/main/Riskanalysis.pdf)

The analysis is summarized in a single-page Power BI dashboard designed to guide intervention strategies.
