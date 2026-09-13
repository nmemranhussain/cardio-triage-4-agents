# Project ACAT (Acute Care Agentic Triage): Cardiovascular Failure Risk Engine & Guideline Copilot

## Basic Information
**Name:** N M Emran Hussain  
**Email:** nmemranhussain2023@gmail.com  
**Date:** July 2026  
**Model Version:** 1.0.0  
**License:** [Apache License Version 2.0,](LICENSE)

## Purpose of this Project
This project instantly analyzes cardiovascular vitals to predict a patient's mortality risk, clearly explain its clinical reasoning, and provide emergency doctors with immediate, guideline-based treatment steps.

## Business Problem & Solution
**Problem:**  
When a heart patient arrives, doctors need to know immediately how dangerous their condition is and what medicine or treatment to start. Manually checking lab tests and guideline manuals takes valuable time.

**Solution:**   
This system eliminates clinical guesswork by transforming chaotic emergency room data into immediate, evidence-based action plans:

- **Automates Data Structuring:** Instantly converts messy, unstructured physician notes and raw lab vitals into clean, standardized patient profiles.

- **Calculates Instant Risk Tiers:** Evaluates complex biomarkers in milliseconds to flag high-risk patients, bypassing the delays of manual threshold checks.

- **Provides Transparent Reasoning:** Uses explainable AI to pinpoint exactly which lab results (like failing kidney function) are driving a critical score, giving doctors immediate context they can trust.

- **Delivers Targeted Care Protocols:** Retrieves exact stabilization steps from established medical guidelines the moment a patient is flagged as critical, standardizing treatment across the emergency department.

- **Monitors Clinical Safety:** Continuously tracks incoming patient data for statistical drift, ensuring the model remains accurate and reliable even if hospital demographics shift over time.

## Intended and Out-of-Scope Usage

**Intended Users:** 
- **Emergency Room Physicians:** To rapidly stratify heart failure risk upon patient intake and receive immediate, guideline-backed stabilization recommendations.
- **Triage Nurses:** To automatically parse unstructured intake notes and prioritize high-risk patients before the attending physician's evaluation.
- **Cardiologists:** To review explainable biomarker drivers (via SHAP values) when consulting on complex or borderline cardiovascular cases.
- **Hospital Administrators & MLOps Engineers:** To monitor real-time clinical dashboards, track department triage wait times, and respond to data drift alerts when patient demographics shift.

**Out-of-scope Uses:**
- **Direct Patient Self-Diagnosis:** The system is exclusively a clinical decision support tool and is not designed or licensed for use by patients without medical training.
- **Definitive Medical Diagnosis:** The predictive ML pipeline provides statistical mortality risk stratification; it does not replace, override, or serve as a legally binding professional clinical judgment.
- **Automated Treatment Execution:** While the RAG agent retrieves evidence-based stabilization protocols, the system cannot automatically prescribe medications, order lab tests, or interface directly with medical hardware.
- **Non-Cardiovascular Triage:** The model is trained strictly on heart failure biomarkers (e.g., ejection fraction, serum creatinine) and cannot be applied to evaluate risk for trauma, respiratory, or neurological emergencies.

## Data Dictionary
**Dataset Name & Source:** [CMS Synthetic Patient Data (OMOP) Dataset](https://console.cloud.google.com/marketplace/product/hhs/synpuf?project=sodium-woodland-473219-u8)  

**Number of Samples:** Key Tables:

- person: Patient demographics. (~2.7 million rows, 18 columns).  
- condition_occurrence: Clinical diagnoses, including cardiovascular conditions. (~11 million rows, 16 columns).
- procedure_occurrence: Records of medical procedures performed on patients. (~33 million rows, 15 columns). 

**Original Features:** 
|Features |
|:--------|
|observation_period_id |
|person_id	|
|observation_period_start_date |
|observation_period_end_date |
|period_type_concept_id |
|condition_occurrence_id |
|person_id_1 |
|condition_concept_id |
|condition_start_date |
|condition_start_datetime |
|condition_end_date |
|condition_end_datetime |
|condition_type_concept_id |
|stop_reason |
|provider_id |
|visit_occurrence_id |
|visit_detail_id |
|condition_source_value |
|condition_source_concept_id |
|condition_status_source_value |
|condition_status_concept_id |

**Engineered Features:** 
|Features |
|:--------|
|observation_period_id 
|person_id |
|observation_period_start_date |
|observation_period_end_date |
}period_type_concept_id |
|condition_occurrence_id |
|condition_concept_id |
|condition_start_date |
|condition_end_date |
|condition_type_concept_id |
|provider_id |
|visit_occurrence_id |
|condition_source_value |
|condition_source_concept_id |
|observation_period_duration_days |
|obs_start_year |
|obs_start_month |
|obs_start_day |
|obs_start_day_of_week |
|condition_start_year |
|condition_start_month |
|condition_start_day |
|condition_start_day_of_week |         
|period_type_concept_id_encoded |         
|condition_concept_id_encoded |  
|condition_type_concept_id_encoded  |
|provider_id_encoded |         
|condition_source_concept_id_encoded |

**Target Feature:** 

## Data Dictionary

|Column Name	      |Modeling Role	|Measurement Level	|Description|
|------------------|--------------|------------------|-----------|

## Training & Test Data

- **Split Ratio:** 
- **Random State:**
- **Total Dataset Size:** 
- **Training Set Size:** 
- **Test Set Size:** 

## Modeling Details

