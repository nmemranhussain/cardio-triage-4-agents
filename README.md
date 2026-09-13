# Project ACAT (Acute Care Agentic Triage): Cardiovascular Failure Risk Engine & Guideline Copilot

## Basic Information
**Name:** N M Emran Hussain  
**Email:** nmemranhussain2023@gmail.com  
**Date:** July 2026  
**Model Version:** 1.0.0  
**License:** [Apache License Version 2.0,](LICENSE)

## Purpose
This project instantly analyzes cardiovascular vitals to predict a patient's mortality risk, clearly explain its clinical reasoning, and provide emergency doctors with immediate, guideline-based treatment steps.

## Business Problem & Solution
**Problem:**  
When a heart patient arrives, doctors need to know immediately how critical their condition is and what treatment to initiate. However, manually cross-referencing raw lab data against extensive clinical protocols consumes valuable time. This manual burden slows down the triage process and leads to inconsistent patient outcomes.

**Solution:**   
An automated, transparent multi-agent triage assistant that instantly calculates a patient's mortality risk level and explains exactly why that score was assigned using clear feature attributions. High-risk patients are identified immediately, providing care teams with evidence-based clinical guidelines the moment they need them most. This system eliminates clinical guesswork by transforming complex, unstructured medical data into immediate, actionable treatment plans:

- **Automated Risk Stratification:** The system instantly categorizes patients into Low, Medium, or High Risk tiers. This solves the core triage problem by showing doctors exactly who needs emergency stabilization and who can safely wait, completely removing manual guesswork.

- **Agent 1 (The Vitals Normalizer):** Instantly scans messy, unstructured physician notes and raw lab results, extracting critical numbers into a clean, standardized data payload so no vital biomarker is overlooked.

- **Agent 2 (The Risk Analyst):** Evaluates the clean data to calculate the exact mortality risk and assign the risk tier. It highlights the specific failing biomarkers (like a dangerously low ejection fraction), proving to the medical team exactly why a patient received their score.

- **Agent 3 (The Guideline Specialist - RAG):** Automatically springs into action the moment a High Risk patient is identified. It searches cardiovascular medical rulebooks and retrieves the exact, evidence-based stabilization steps tailored to the patient's condition.

- **Agent 4 (The Reporting Auditor):** Packages the parsed vitals, the explainable risk tier, and the retrieved treatment guidelines into one clean, actionable dashboard alert, ensuring the care team can start the right interventions immediately.

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

