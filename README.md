# Password Analysis — Cybersecurity Lab 02

## Overview

This project explores password security analysis and anomaly detection through a simulated corporate password audit.

The objective is to identify **mass password reuse** by detecting password hashes shared by an unusually large number of accounts.

## Objectives

- Analyze password length and strength using `zxcvbn`.
- Identify password reuse across multiple accounts.
- Investigate suspicious password-setting activity over time.
- Design a threshold-based detection rule.
- Evaluate detection performance using confusion matrices, precision, recall, and false positives.

## Detection Approach

The detection rule flags accounts whose password hash is shared by at least a threshold number of accounts.

The threshold is calibrated using a baseline audit:

`T = max(10, 2 × largest normal cluster)`

The rule uses password hashes rather than plaintext passwords to identify shared credentials.

## Visualizations

The notebook includes:

- Password length and strength distributions.
- Password strength by department.
- The largest shared-password clusters.
- Password-setting events over time.
- Confusion matrices and threshold sensitivity analysis.

## Evaluation

The rule is evaluated on a simulated audit containing normal accounts and injected anomalous accounts, as well as a separate clean dataset.

Metrics include:

- **Precision:** proportion of flagged accounts that are anomalous.
- **Recall:** proportion of anomalous accounts successfully detected.
- **False positives:** normal accounts incorrectly flagged.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- zxcvbn
- Jupyter Notebook

## Repository Contents

- `password_analysis.ipynb` — analysis, detection rule, and visualizations.
- `report.pdf` — lab report.

## Disclaimer

This project uses simulated audit data for educational purposes. The results demonstrate the detection approach on the provided datasets and do not guarantee equivalent performance in real-world environments.
