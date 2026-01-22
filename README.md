# SmartDischarge: Early Prediction of ICU Readmission Risk  

## Project Overview
Unplanned ICU readmissions are a significant source of preventable harm, clinician burden and healthcare system cost. Nurses are often the first to sense that something’s not right, yet existing predictive models are sometimes not integrated into real clinical workflows.

SmartDischarge is a nurse-centered, data-driven risk scoring tool that predicts the probability of ICU readmission within 48 hours of discharge. Our goal is to support proactive intervention and safer discharge planning by providing interpretable, real-time risk signals that can be easily integrated into nursing workflows.

This project was developed as part of the Smarter Care Datathon at the University of Pennsylvania.

---

## Early Prediction of Patient Outcomes

Key Question:
How can we predict early which ICU patients are at risk of deterioration so clinicians can intervene proactively?

We focused specifically on ICU readmission risk within 48 hours, a clinically meaningful outcome associated with higher mortality, longer hospital stays and increased costs.

---

## Data Source
We used data derived from MIMIC-IV, a large, publicly available, de-identified electronic health record (EHR) dataset containing detailed ICU and hospital data from Beth Israel Deaconess Medical Center.

Dataset characteristics:
- Over 9,000 patient records used for modeling
- Real-world EHR data reflecting actual clinical documentation practices
- Includes demographics, vitals, labs, medications and care-related variables
- Suitable for developing clinically relevant and generalizable models

We assessed the dataset for:
- Relevance: Variables aligned with clinical decision-making
- Completeness: Sufficient coverage across patient encounters
- Quality: Realistic distributions consistent with ICU practice
- Adequacy: Large enough sample size to support machine learning models

---

## Modeling Approach
We framed ICU readmission prediction as a binary classification problem.

### Model
- XGBoost 
- Selected for its strong performance on tabular clinical data and interpretability

### Feature Selection
- Final model uses 11 key features
- Features were selected based on:
  - Statistical relevance
  - Feature importance rankings
  - Clinical interpretability

### Validation
- Statistical tests were conducted to ensure features were not trivially dependent
- Model performance was evaluated using standard classification metrics
- Emphasis was placed on stability and practical deployability rather than maximizing a single metric

---

## Key Results
- Successfully built a predictive model that estimates 48-hour ICU readmission risk
- Identified a compact set of clinically meaningful predictors
- Demonstrated that accurate risk stratification is possible using routinely available EHR data
- Model design is customizable and can be adapted to:
  - Different hospital settings
  - Alternative outcome windows
  - Additional patient-level variables

---

## Clinical Relevance & Design Philosophy
Unlike many purely academic predictive models, SmartDischarge was designed with nurses as the primary users.

Design principles:
- Nurse-centered and workflow-aware
- Interpretable risk scores rather than black-box predictions
- Intended for real-time or near–real-time use
- Supports — not replaces — clinical judgment

The tool is envisioned as a decision-support layer that flags elevated risk early, enabling timely interventions such as closer monitoring, delayed discharge, or care escalation.

---

## Future Work
- External validation on additional hospital datasets
- Prospective evaluation in clinical settings
- Integration with live EHR systems
- Expansion to other outcomes (e.g., mortality, length of stay)
- Fairness and bias analysis across patient subgroups

---

## Disclaimer
This project was developed for research and educational purposes only and is not intended for direct clinical deployment without further validation and regulatory review.
