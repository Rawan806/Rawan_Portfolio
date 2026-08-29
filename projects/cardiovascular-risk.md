# Early Cardiovascular Disease Classification

## Overview

This project explored machine-learning approaches for early cardiovascular disease classification using a structured patient dataset containing approximately **70K records**.

The goal was to build and compare multiple classification models while examining preprocessing, feature engineering, model selection, and evaluation.

## My Work

The project included:

- Data-quality inspection
- Duplicate and invalid-value handling
- Blood-pressure validation
- Age conversion from days to years
- BMI feature engineering
- Feature scaling
- Model comparison
- Cross-validation
- Hyperparameter tuning using GridSearchCV

## Models Evaluated

I compared:

- Logistic Regression
- Support Vector Machine
- Random Forest

The models were evaluated using metrics including accuracy, F1-score, and ROC-AUC.

## Results

The strongest final model was a tuned **Random Forest**.

**Final performance:**

- Accuracy: **73.65%**
- ROC-AUC: **0.8015**

The selected configuration used hyperparameter tuning and provided the strongest overall test performance among the evaluated classical machine-learning approaches.

## Limitations

The project is an academic machine-learning study and should not be interpreted as a clinical diagnostic system.

Performance would require external validation, broader clinical evaluation, and careful consideration of medical deployment requirements before any real-world use.

## Tech Stack

Python · Pandas · NumPy · scikit-learn · GridSearchCV · Matplotlib · Jupyter

## Repository

[View repository →](https://github.com/Rawan806/ML-early-risk-prediction)
