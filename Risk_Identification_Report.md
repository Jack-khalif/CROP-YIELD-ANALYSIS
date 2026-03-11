# Risk Identification Report – Agricultural Insurance

**Prepared by:** Jackson Mugwe  
**Date:** March 2026  
**Project:** Crop Yield Quality Assurance & Risk Analysis  
**Dataset Size:** 10,000 Records (Kenya-relevant variables)

**GitHub Repository:**  
https://github.com/Jack-khalif/CROP-YIELD-ANALYSIS

---

# Executive Summary

After completing full **data quality checks following an improved Standard Operating Procedure (SOP)**, the dataset was confirmed to be **100% clean**:

- Zero missing values  
- Zero duplicates  
- Zero outliers  
- Zero invalid planting or harvest dates  

However, a **critical risk for crop insurance modeling emerged**.

Crop yield was found to be **almost completely uncorrelated with all traditional agronomic and environmental factors**.

This finding mirrors a **real challenge in agricultural insurance**, particularly when working with **smallholder farmers across Africa**.

Poor predictability leads to:

- inaccurate premium pricing
- unexpected insurance claims
- difficulty identifying risk zones

## Key Risk Identified

Traditional field survey data alone **cannot reliably forecast crop yields or trigger insurance payouts**.

## Recommended Solution

Integrate **satellite-derived vegetation indices (NDVI/EVI)** with **farmer-reported practices collected via mobile data tools** such as **KoboToolbox**.

This hybrid data approach is already used by organizations working in agricultural insurance across Africa.

---

# 1. Data Quality Summary (SOP Compliance)

All standard **data integrity checks** were performed.

| Check Category | Result |
|----------------|-------|
| Duplicate records | 0 |
| Invalid planting/harvest dates | 0 |
| Outliers (Yield, Rainfall, N, P, K, Temperature) | 0 |
| Categorical consistency (Region, Crop Type, Soil Type) | 100% clean |
| Missing values | 0 |

### Conclusion

The dataset meets **enterprise-grade data quality standards**.

No evidence of **field agent reporting errors or training gaps** was detected in this sample.

---

# 2. Risk Analysis – Correlation with Crop Yield

The following correlation analysis was performed to determine which variables influence yield outcomes.

| Factor | Correlation with Yield |
|------|------|
| Potassium (K) | +0.0087 |
| Rainfall | +0.0078 |
| pH | +0.0029 |
| Temperature | +0.0024 |
| Nitrogen (N) | -0.0002 |
| Phosphorus (P) | -0.0101 |
| NDVI | -0.0161 |

### Interpretation

All correlations are **statistically negligible (< 0.02)**.

In agricultural insurance modeling, this represents a **high-severity analytical risk** because:

- Yield variation **(1.0 – 9.99 t/ha)** cannot be explained using measurable variables.
- Insurance pricing models would become **unreliable**.
- Risk pools may experience **unexpected claim spikes**.
- Farmers may **lose trust** if claims are denied due to inaccurate predictions.

---

# 3. Business Impact

### Claims Risk
Sudden yield drops or unusually high production cannot be predicted, increasing the likelihood of **loss ratio volatility**.

### Pricing Risk
Premium calculations based on current field variables would be **unreliable**.

### Operational Risk
Field agents may be collecting **data that contributes little predictive value**.

### Strategic Opportunity

This analytical gap strongly supports the **integration of satellite and mobile technologies**.

This project demonstrates that **data integration is not optional — it is essential** for reliable agricultural insurance modeling.

---

# 4. Proposed Solutions & Process Improvements

## Immediate Actions (0–30 Days)

- Flag any new dataset upload with **Yield < 2 t/ha** for manual verification.
- Implement an **automated correlation monitoring script** within the internal data platform.

(Python script already prepared in the project repository.)

---

## Medium-Term Improvements (30–90 Days)

- Integrate **satellite NDVI/EVI indicators** directly into survey workflows.
- Pre-fill satellite data in **KoboToolbox survey forms using API connections**.

Add the following farmer-reported variables:

1. Irrigation effectiveness
2. Pest outbreak occurrence (Yes / No)
3. Distance to nearest agricultural market

These variables provide **important explanatory signals missing from the current dataset**.

---

## Long-Term Improvements

Develop a **regional agricultural risk dashboard** using Power BI with:

- automated regional alerts
- crop yield monitoring
- insurance claim risk indicators

A prototype dashboard has already been developed as part of this portfolio project.

A pilot implementation could begin in **one Kenyan county** to measure improvements in predictive accuracy.

---

# 5. Recommendations for Field Staff Training

To strengthen data reliability across survey operations:

### New Field Checklist

Develop a **1-page checklist for enumerators** titled:

**“What to Do When Yield Data Appears Suspicious.”**

### Training Focus Areas

- Encourage **honest reporting**, even when yields are low.
- Train agents to **capture field photographs via mobile survey tools**.
- Use images for **satellite validation and quality verification**.

---

# 6. Effectiveness Evaluation Plan

Following implementation of new data fields and SOP improvements:

1. Collect **10,000 additional farmer records**.
2. Re-run correlation and regression analysis.
3. Measure improvement in model performance.

### Target Outcome

Increase **explained variance (R²)**:

Current model performance  
≈ **0% explanatory power**

Target after integration  
**>30% predictive power within one growing season**

---

# Author

**Jackson Mugwe**  
Data Analyst  
Nairobi, Kenya
.
