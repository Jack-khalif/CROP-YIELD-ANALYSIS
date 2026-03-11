Risk Identification Report – Agricultural Insurance
Prepared by: Jackson Mugwe
Date: March 2026
Project: Crop Yield Quality Assurance & Risk Analysis (10,000 records, Kenya-relevant variables)
GitHub link github.com/Jack-khalif/CROP-YIELD-ANALYSIS/Risk_Identification_Report.md
Executive Summary
After completing full data quality checks following an improved SOP, the dataset is 100% clean (zero missing values, duplicates, outliers, or invalid dates). However, a critical risk for crop insurance emerged: yield is almost completely uncorrelated with all standard agronomic and environmental factors.
This finding directly mirrors real-world challenges faced by Pula when insuring smallholders — poor predictability leads to inaccurate premium pricing and unexpected claims.
Key Risk Identified: Traditional field data alone cannot reliably forecast yields or trigger insurance payouts.
Recommended Solution: Integrate satellite-derived indices (NDVI/EVI) with farmer-reported practices collected via mobile tools (KoboToolbox) — exactly the technology Pula already uses across Africa.
1. Data Quality Summary (SOP Compliance)
Duplicates: 0
Invalid Harvest/Planting dates: 0
Outliers (Yield, Rainfall, N, P, K, Temperature): 0
Categorical consistency (Regions, Crops, Soils): 100% clean
Missing values: 0
Conclusion: Data meets enterprise standards. No field-agent training gaps detected here.
2. Risk Analysis – Correlation with Yield

FactorCorrelation with YieldPotassium (K)+0.0087Rainfall+0.0078pH+0.0029Temperature+0.0024Nitrogen (N)-0.0002Phosphorus (P)-0.0101NDVI-0.0161
Interpretation:
All correlations are statistically negligible (< 0.02). In agricultural insurance this is a high-severity risk because:

Yield variation (1.0 – 9.99 t/ha) cannot be explained by measurable field data.
Insurance models would either over-price policies or face massive unexpected payouts.
Smallholder farmers in Kenya/Africa would lose trust if claims are denied due to inaccurate predictions.

3. Business Impact 

Claims Risk: High-yield outliers or sudden drops cannot be predicted → potential loss ratio spikes.
Pricing Risk: Premiums based on these variables would be unreliable.
Operational Risk: Field agents waste time collecting data that adds almost no value.
Opportunity: This gap is exactly why it is needed to use satellite + mobile tech ,my  analysis proves it is not optional, it is essential.

4. Proposed Solutions & Process Improvements

Immediate (0–30 days)
Flag any new upload with Yield < 2 t/ha for manual review.
Add automated correlation check in the in-house data tool (Python script ready).

Medium-term (30–90 days)
Integrate satellite NDVI/EVI directly into KoboToolbox forms (pre-filled via API).
Add 3 new farmer-reported questions: “Irrigation effectiveness”, “Pest outbreak yes/no”, “Market access distance”.

Long-term
Build a simple risk dashboard in Power BI (already prepared from this project) with alerts by Region.
Pilot in one Kenyan county and measure improvement in yield prediction accuracy.


5. Recommendations for Field Staff Training

New 1-page checklist: “What to do when yield data looks suspicious” (draft attached in portfolio).
Emphasize honest reporting — even if yield seems low.
Train on using the mobile app to capture photos of fields (for later satellite cross-check).

6. Effectiveness Evaluation Plan

After implementing new fields and SOP, re-run correlation analysis on next 10k records.
Target: increase explained variance (R²) from ~0% to >30% within one season.

Signed,
Jackson Mugwe
Data Analyst , Nairobi, Kenya
Available immediately for remote role (±3h EAT)
