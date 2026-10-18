# Project ACAT: Academic Clinical Predictive Analytics Tool

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![Python](https://img.shields.io/badge/python-3.10%2B-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()
[![Methodology](https://img.shields.io/badge/approach-Leakage--Free%20Temporal%20Prediction-orange.svg)]()

## Overview

**Project ACAT** is a rigorous, health informatics framework designed to build transparent, prospective clinical risk stratification models using large-scale electronic health record (EHR) data. Leveraging synthetic OMOP Common Data Model (CDM) datasets hosted on Google BigQuery, this project emphasizes strict adherence to clinical machine learning best practices—specifically **preventing target leakage via temporal observation windows** and **patient-level group splitting**.

---

## Repository Architecture

```text
cardio-triage-4-agents/
│
├── data/                               # Raw and processed dataset samples
│   └── sample_condition_occurrence.csv
│
├── notebooks/                          # Chronological research pipelines
│   ├── 01_acat_baseline_risk_stratification.ipynb
│   └── 02_acat_advanced_lgbm_calibration.ipynb
│
├── evaluation/                         # Exported model evaluation artifacts & plots
│   └── shap_summary_bar.png
│
└── README.md                           # Project documentation
```
