# Project Summary
## Crop Yield Data Quality & Risk Analysis for Agricultural Insurance

**Author:** Jackson Mugwe Waithaka  
**Location:** Nairobi, Kenya  
**Date:** March 2026  
**Dataset:** 10,000 Agricultural Production Records

---

# Problem Statement

Agricultural insurance providers rely on farmer survey data to estimate crop yields and determine risk levels.

However, smallholder farming systems are complex and often produce **highly variable outcomes that are difficult to predict using traditional field variables alone.**

If data quality is weak or predictive signals are poor, insurers face several risks:

- inaccurate premium pricing
- delayed claims
- loss of trust from farmers
- unexpected loss ratios

This project evaluates **data quality and predictive risk signals in agricultural yield datasets.**

---

# Approach

The project implemented a structured analytics workflow:

1. Developed an improved **Data Quality Standard Operating Procedure (SOP)**
2. Performed **automated validation checks** on the dataset
3. Conducted exploratory analysis and visualization
4. Evaluated correlations between crop yield and agronomic variables
5. Produced a **risk identification report**
6. Designed a **field staff training guide** to improve future data collection

---

# Key Findings

### 1. Dataset Quality

The dataset passed all standard validation checks:

- No duplicate records
- No missing values
- No invalid planting/harvest dates
- No extreme outliers detected

This indicates **high data integrity from field surveys.**

---

### 2. Weak Predictive Relationships

Despite strong data quality, crop yield showed **extremely weak correlation (<0.01)** with key variables including:

- rainfall
- soil nutrients (NPK)
- temperature
- soil pH

This suggests that **traditional survey variables alone cannot reliably predict yield outcomes.**

---

# Business Risk Implications

For agricultural insurance systems, this creates several operational risks:

**Prediction Risk**

Yield models may have very low explanatory power.

**Pricing Risk**

Insurance premiums based only on field variables may be poorly calibrated.

**Claims Volatility**

Unexpected yield drops could lead to sudden claim spikes.

---

# Recommended Actions

### Immediate

- Implement automated data validation pipelines.
- Flag suspicious yield records during ingestion.

---

### Medium-Term

- Expand farmer surveys with additional questions:
  - irrigation effectiveness
  - pest outbreaks
  - distance to markets

---

### Strategic

Integrate **satellite-derived vegetation indicators (NDVI/EVI)** to improve predictive accuracy.

Combining **remote sensing data with field surveys** is likely to produce stronger yield models.

---

# Project Deliverables

This repository contains:

- Data Quality SOP
- Risk Identification Report
- Field Staff Training Guide
- Data Analysis Notebooks

These components simulate a **complete analytics workflow for agricultural insurance data operations.**

---

# Author

Jackson Mugwe Waithaka  
Data Analyst  
Nairobi, Kenya
