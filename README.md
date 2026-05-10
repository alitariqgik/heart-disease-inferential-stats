# heart-disease-inferential-stats
Heart Disease Prediction

> Naive Bayes \\\& Bayesian Network Analysis on the UCI Heart Disease Dataset  
> Ghulam Ishaq Khan Institute of Engineering and Technology | Faculty of Computer Sciences and Engineering

Table of Contents
Project Overview
Repository Structure
Dataset
Bayesian Network Architecture
Project Deliverables
Dependencies
How to Run
Results
Key Concepts Covered
Authors


Project Overview

This project applies inferential statistics and probabilistic graphical modeling to the problem of heart disease prediction. Two complementary approaches are implemented and compared:
Approach	Description
Naive Bayes (From Scratch)	Mixed Naive Bayes with Gaussian likelihoods for numerical features and Laplace-smoothed categorical likelihoods for discrete features
Naive Bayes (sklearn)	Baseline GaussianNB from scikit-learn applied to all features
The project also includes a fully specified 4-layer Bayesian Network  that models the causal progression from patient demographics → physiological risk factors → clinical symptoms → final diagnosis.

Repository Structure

heart-disease-inferential-stats/
│
├── INFERENTIAL_PROJECT.ipynb          # Main notebook: implementation & evaluation
│
├── docs/
│   ├── Conceptual_Modeling.docx       # Section 1: Variable definitions & Bayesian Network design
│   ├── Independence_Analysis.docx     # Section 2: Feature selection & independence violations
│   └── Information_Flow_Demonstration.docx  # Section 3: Causal, evidential & inter-causal flow
│
├── heart_disease.csv                  # Dataset (auto-downloaded by notebook if absent)
│
└── README.md

Dataset

Source: UCI Heart Disease Dataset (Cleveland) — accessed via GitHub mirror  
URL: `https://raw.githubusercontent.com/dsrscientist/dataset1/master/heart.csv`
The dataset contains medical attributes of patients used to predict the presence or absence of heart disease.
Variable	Name	Type	Description

X1	Age	Numerical	Age in years
X2	Sex	Categorical (Binary)	0 = Female, 1 = Male
X3	cp (Chest Pain Type)	Categorical	1–4 pain categories
X4	chol (Cholesterol)	Numerical	Serum cholesterol in mg/dl
X5	thalach (Max Heart Rate)	Numerical	Max HR achieved during exercise
X6	exang (Exercise Angina)	Categorical (Binary)	0 = No, 1 = Yes
X7	oldpeak (ST Depression)	Numerical	ECG ST segment depression
X8	ca (Major Vessels)	Numerical/Categorical	Number of major vessels (0–3)
Y	target_binary	Binary	0 = No disease, 1 = Disease

Project Deliverables

1. Conceptual Modeling (Conceptual_Modeling.docx)
2. 
Formal variable definitions with probabilistic types
Full Bayesian Network DAG structure with causal justification
Naive Bayes independence assumption analysis (where it holds vs. fails)


3. Independence & Feature Analysis (Independence_Analysis.docx)
4. 
Correlation-based feature selection
Identified independence violations:
Age ↔ Cholesterol (structural positive correlation)
Exercise Angina ↔ ST Depression (shared cause: Max Heart Rate)
Model comparison: Full features vs. reduced feature set
Performance impact analysis



5. Information Flow Demonstration (Information_Flow_Demonstration.docx)
6. 
Case (a): Causal Flow — `Age → Cholesterol → Chest Pain`
Case (b): Evidential Flow — `Exercise Angina ← Max HR → ST Depression`
Case (c): Inter-causal Flow (Explaining Away) — `Chest Pain → Heart Disease ← ST Depression`
Prior and posterior probability tables for each case



7. Implementation Notebook (INFERENTIAL_PROJECT.ipynb)
   
Part 1: Mixed Naive Bayes from scratch (Gaussian + Categorical likelihoods)
Part 2: sklearn GaussianNB baseline
Part 3: Side-by-side comparison with full metrics


Dependencies
Python Version

Python >= 3.8

Required Libraries
`txt
numpy>=1.21.0
pandas>=1.3.0
scikit-learn>=0.24.0

Install all dependencies at once:
bash

pip install numpy pandas scikit-learn

No additional packages required.The dataset is auto-downloaded by the notebook on first run via `urllib`.

How to Run

Jupyter Notebook
bash
1. Clone the repository
git clone https://github.com/alitariqgik/heart-disease-inferential-stats.git
cd heart-disease-inferential-stats
2. Install dependencies
pip install numpy pandas scikit-learn jupyter
3. Launch Jupyter
jupyter notebook INFERENTIAL_PROJECT.ipynb

Key Concepts Covered

Bayesian Networks — Directed Acyclic Graphs for probabilistic reasoning
Naive Bayes Classifier — From-scratch implementation with mixed likelihoods
Laplace Smoothing — Handling unseen categorical values
Conditional Independence — Analysis of where the Naive Bayes assumption holds and fails
Information Flow — Causal, evidential, and inter-causal (explaining away) propagation
Feature Selection — Correlation-based pruning of weak predictors
Model Comparison — Full vs. reduced feature set evaluation

License
This project is submitted as academic coursework. Dataset is publicly available from the UCI Machine Learning Repository.
