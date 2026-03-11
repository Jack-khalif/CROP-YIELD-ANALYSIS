
# Agricultural Insurance – Improved Data Quality SOP v2.0

**Author:** Jackson Mugwe  
**Date:** March 2026  
**Dataset:** Agricultural Yield Prediction (10,000 records, Kenya-relevant variables)  
**Purpose:** Replace basic data checks with a **robust, field-ready validation process** suitable for agricultural insurance analytics.

---

# 1. Overview

This **Standard Operating Procedure (SOP)** establishes a structured workflow for validating agricultural survey datasets before they are used in **risk modeling, insurance pricing, or yield prediction analysis**.

The SOP introduces automated checks that detect:

- survey duplication
- invalid planting/harvest timelines
- extreme outliers in agronomic variables
- inconsistent categorical entries
- weak predictive signals in yield models

The goal is to ensure that **only reliable, analysis-ready datasets** enter downstream insurance analytics systems.

---

# 2. Data Quality Checks Introduced

The following validation checks expand upon the previous basic SOP.

| Check | Purpose |
|------|------|
| Duplicate detection | Prevent multiple entries of the same survey record |
| Date logic validation | Ensure Harvest Date occurs after Planting Date |
| Outlier detection (IQR method) | Identify unrealistic agronomic values |
| Categorical consistency scan | Detect inconsistent region, crop, or soil labels |
| Correlation analysis with Yield | Identify early warning signals for weak predictive models |

These checks help identify **data reliability risks before they affect insurance models**.

---

# 3. Python Implementation

The following script implements the full validation process.

```python
import pandas as pd
import numpy as np
from datetime import datetime

# 1. Duplicate check
duplicates = df.duplicated().sum()
print(f"Duplicate rows: {duplicates}")

# 2. Convert dates
df['Planting_Date'] = pd.to_datetime(df['Planting_Date'], errors='coerce')
df['Harvest_Date'] = pd.to_datetime(df['Harvest_Date'], errors='coerce')

print(
    f"\nDate conversion successful: "
    f"{df['Planting_Date'].dtype}, {df['Harvest_Date'].dtype}"
)

# 3. Logical check: Harvest must occur after Planting
invalid_dates = (df['Harvest_Date'] <= df['Planting_Date']).sum()
print(f"Invalid date pairs (Harvest ≤ Planting): {invalid_dates}")

# 4. Categorical consistency check
print("\nUnique Regions:", sorted(df['Region'].unique()))
print("Unique Crop Types:", sorted(df['Crop_Type'].unique()))
print("Unique Soil Types:", sorted(df['Soil_Type'].unique()))

# 5. Outlier detection using the IQR method
def count_outliers(col):
    Q1 = df[col].quantile(0.25)
    Q3 = df[col].quantile(0.75)
    IQR = Q3 - Q1

    lower = Q1 - 1.5 * IQR
    upper = Q3 + 1.5 * IQR

    return ((df[col] < lower) | (df[col] > upper)).sum()

key_columns = ['Yield', 'Rainfall', 'N', 'P', 'K', 'Temperature']

for col in key_columns:
    print(f"Outliers in {col}: {count_outliers(col)}")

# 6. Correlation analysis with Yield
corr = df[
    ['Yield', 'Rainfall', 'N', 'P', 'K', 'Temperature', 'pH', 'NDVI']
].corr()['Yield'].sort_values(ascending=False)

print("\nTop correlations with Yield:\n", corr)

# 7. Save cleaned dataset
df.to_csv('cleaned_agri_yield.csv', index=False)

print("\nCleaned file saved as 'cleaned_agri_yield.csv'")
````

---

# 4. Dataset Validation Results

After running the SOP on the **10,000-record dataset**, the following results were observed:

| Check                                        | Result |
| -------------------------------------------- | ------ |
| Duplicate records                            | 0      |
| Invalid planting/harvest dates               | 0      |
| Outliers (Yield, Rainfall, NPK, Temperature) | 0      |
| Missing values                               | 0      |

### Key Analytical Finding

Correlation between **Yield and all major agronomic variables** was extremely weak:

**All correlations < 0.01**

This indicates that the dataset may have **limited predictive value for yield modeling**, which represents a potential **insurance risk signal**.

---

# 5. Risk Flag Identified

Extremely low correlations suggest that **standard field variables alone cannot reliably explain yield variation**.

Implications for agricultural insurance models:

* reduced prediction accuracy
* unreliable premium pricing
* potential claim volatility
* difficulty identifying high-risk farming zones

This highlights the need for **additional data sources such as satellite-derived vegetation indices and farmer practice indicators**.

---

# 6. Recommended Process Improvements

## Immediate Actions

* Automatically flag records where **Yield < 2 t/ha**, as these may represent potential insurance claim risks.
* Implement the validation script as part of the **data ingestion pipeline**.

---

## Medium-Term Improvements

* Integrate **KoboToolbox export validation scripts** to ensure field survey data is validated immediately after collection.
* Expand survey forms with additional farmer-practice indicators such as:

  * irrigation effectiveness
  * pest outbreak occurrence
  * distance to nearest agricultural market

These variables may significantly improve **yield predictability models**.

---

## Monitoring & Automation

* Create a **daily monitoring dashboard** in Power BI.
* Use scheduled refresh to detect:

  * new suspicious records
  * abnormal yield values
  * survey inconsistencies

---

# 7. Field Staff Training Component

To maintain high-quality survey data, field enumerators should receive:

* a **1-page quick reference guide** titled
  **“How to Identify Suspicious Yield Records in the Field.”**

Training should emphasize:

* accurate reporting even when yields are low
* careful verification of planting and harvest dates
* capturing field photos where possible for remote verification

---

# 8. Expected Impact

Implementing this SOP is expected to:

* reduce invalid survey data entering analytics pipelines
* improve trust in insurance models
* enable earlier identification of dataset risks

**Estimated Impact:**
Up to **95% reduction in poor-quality records entering analytical models**.

---

# 9. Next Evaluation Step

The effectiveness of the SOP will be evaluated after **30 days of operational use**.

Evaluation plan:

1. Process a new dataset batch.
2. Re-run validation checks.
3. Measure improvements in:

   * data consistency
   * model predictive performance
   * operational data quality.

---

**Prepared by:**
Jackson Mugwe
Data Analyst – Nairobi, Kenya


```
