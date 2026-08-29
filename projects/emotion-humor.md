# Emotion-Aware Humor Classification

## Overview

This project investigated whether weak emotion information could provide additional predictive signal for humor classification.

The modeling experiments used a balanced dataset of **200,000 samples**, containing 100K humor and 100K non-humor examples.

## My Contribution

My work focused on the downstream machine-learning and evaluation stage.

I built and compared:

- Logistic Regression
- Multinomial Naive Bayes
- Linear SVM

Two feature configurations were evaluated:

1. TF-IDF text features only
2. TF-IDF text features combined with one-hot encoded weak-emotion labels

## Experimental Setup

The dataset was split into:

- **160K training samples**
- **40K test samples**

Performance was evaluated using:

- Accuracy
- Macro-F1
- Classification reports
- Confusion matrices

## Results

The strongest configuration was:

**Linear SVM + Text + Weak Emotion**

- Accuracy: **94.95%**
- Macro-F1: **94.95%**

The weak-emotion signal produced a particularly noticeable improvement for Linear SVM, increasing performance from approximately **92.85% to 94.95%**.

This suggests that even noisy auxiliary emotion information can provide useful signal when combined with strong text representations.

## Tech Stack

Python · scikit-learn · TF-IDF · Linear SVM · Logistic Regression · Multinomial Naive Bayes · Pandas · Jupyter

## Repository

Source repository is currently private.
