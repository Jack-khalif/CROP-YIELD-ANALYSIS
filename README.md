

# Crop Yield Data Quality & Risk Analysis for Agricultural Insurance

**Author:** Jackson Mugwe Waithaka  
**Location:** Nairobi, Kenya  
**Project Type:** Data Quality Engineering & Agricultural Risk Analytics  
**Dataset Size:** 10,000 Agricultural Records

---

# Project Overview

This project analyzes agricultural production data to evaluate **data quality, risk signals, and predictive limitations in crop yield datasets used for agricultural insurance.**

Crop insurance systems that support smallholder farmers depend heavily on **accurate field survey data**. Poor data quality can lead to:

- incorrect insurance pricing
- unreliable yield predictions
- delayed claim processing
- loss of trust from farmers

This project simulates a real-world **data operations workflow for agricultural insurance analytics**, combining:

- data quality engineering
- exploratory analysis
- operational reporting
- field staff training design

---

# Project Objectives

The project was designed to achieve the following goals:

- implement a **robust data validation Standard Operating Procedure (SOP)**
- detect survey data issues before they affect analytical models
- analyze relationships between crop yield and agronomic variables
- identify risks affecting agricultural insurance prediction systems
- design operational improvements for **field survey workflows**

---

# Dataset Description

The dataset contains **10,000 agricultural production records** with variables typically collected from smallholder farmer surveys.

Key variables include:

- Crop Yield (t/ha)
- Rainfall
- Soil pH
- Nitrogen / Phosphorus / Potassium (NPK)
- Temperature
- NDVI vegetation index
- Crop Type
- Soil Type
- Region
- Planting Date
- Harvest Date

These variables represent common inputs used in **agricultural monitoring and insurance risk models.**

---

# Tools & Technologies

The project was implemented using:

### Data Analysis

- Python
- Pandas
- NumPy
- Jupyter Notebook

### Data Quality Engineering

- automated validation scripts
- IQR outlier detection
- date consistency checks
- categorical integrity validation

### Documentation & Reporting

- Markdown technical reports
- operational SOP documentation
- field training materials

---

# Repository Structure



CROP-YIELD-ANALYSIS

│
├── README.md
│
├── notebooks
│   ├── visualization_analysis.ipynb
│   └── SOP_validation.ipynb
│
├── Risk_Identification_Report.md
│
├── Agricultural_Data_Quality_SOP.md
│
├── training.md
│
└── dataset_files



---

# Key Project Documents

### Risk Identification Report

A structured business analysis describing **critical risks discovered during yield modeling.**

Main finding:

> Crop yield showed extremely weak correlation with traditional agronomic variables.

This presents potential risks for **insurance prediction models.**

---

### Data Quality SOP

A **production-ready validation framework** designed to ensure agricultural datasets meet enterprise data quality standards.

The SOP includes:

- duplicate detection
- planting/harvest date validation
- outlier detection
- categorical consistency checks
- correlation-based risk monitoring

---

### Field Staff Training Guide

A practical training document designed to help **survey enumerators collect reliable field data.**

The guide introduces:

- mandatory survey checklists
- photo verification procedures
- new farmer questions
- risk flagging protocols

Improving field data collection strengthens the **entire insurance analytics pipeline.**

---

# Key Analytical Finding

Despite strong data quality, the analysis revealed an important insight.

Crop yield was found to have **extremely weak correlations (<0.01)** with common agronomic variables including:

- rainfall
- soil nutrients
- temperature
- soil pH

This indicates that **traditional survey variables alone may not be sufficient for reliable yield prediction.**

---

# Risk Implications for Agricultural Insurance

This discovery highlights several operational risks.

### Prediction Risk

Yield prediction models may have **very low explanatory power**.

### Pricing Risk

Insurance premiums based only on field variables could be **poorly calibrated**.

### Claims Risk

Unexpected yield shocks may create **unpredictable claim spikes.**

---

# Recommended Improvements

Based on the analysis, several improvements were proposed.

### Immediate Improvements

- integrate automated data validation scripts
- flag suspicious yield values during ingestion

### Medium-Term Improvements

- expand survey forms with additional farmer variables
- improve enumerator training and reporting guidelines

### Strategic Data Integration

Future models should integrate **satellite-derived vegetation indicators** such as NDVI and EVI to improve yield prediction accuracy.

---

# Future Work

Possible extensions of this project include:

- building an automated **data quality monitoring pipeline**
- integrating **satellite crop monitoring datasets**
- developing an **interactive analytics dashboard**
- training machine learning models for yield prediction

---

# About the Author

Jackson Mugwe Waithaka  
Data Analyst – Nairobi, Kenya

Background in engineering and data analytics with strong interest in:

- agricultural technology
- development data systems
- insurance risk analytics
- data-driven solutions for emerging markets

---

# Contact

GitHub  
https://github.com/Jack-khalif

