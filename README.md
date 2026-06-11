# Exploring Treatment Patterns and Cardiovascular Risk Factors in Prostate Cancer Patients Receiving Novel Hormonal Therapies

**Stats 170B Capstone Project** | Trian Gunney, Kara Statham, Lizbeth Ramirez, Tiffany Kong

---

## How to Run

1. Clone the repository
2. Open notebooks/models/model_demo.ipynb 
   * This is the demo notebook demonstrating the types of analysis we conducted
3. Run all cells (< 1 minute) 

---

## Demo Notebook

`notebooks/models/model_demo.ipynb` — [(HTML version)](notebooks/models/model_demo.html)

Demonstrates cardiovascular risk identification using elastic net logistic regression. Loads sample data, generates predictions, and shows examples of correct and incorrect classifications.

---

## Repository Structure

* All data is stored in the 'data' directory.
* All Jupyter Notebooks are stored in the 'notebook' directory, with preprocessing notebooks in the main 'notebook' directory and notebooks for the 2 independent analyses (Risk Stratification & Clinical Insight) stored in their respective sub-directories.

### `data/`
| File | Description |
|------|-------------|
| `column_key.csv` | Index of full and abbreviated variable names |
| `raw/Cardio_onc_prostate_students.xlsx` | Raw patient data from Dr. Kaakour (restricted) |
| `processed/cardio_onc_prostate_02processed.csv` | Cleaned column names, fixed column types |
| `processed/cardio_onc_prostate_03cleaned.csv` | Removed columns with excessive null values |
| `processed/cardio_onc_prostate_04cleaned.csv` | Response variable added, binary types converted, treatment names standardized |
| `processed/cardio_onc_prostate_06_broad_clean.csv` | Final cleaned dataset used for clinical analyses |
| `sample/sample_data.csv` | Synthetic sample data for demo notebook |

---

### `notebooks/` — Preprocessing

| Notebook | Description |
|----------|-------------|
| `01_data_cleaning.ipynb` | Inspect data types and structure, create column names, report missingness |
| `02_data_cleaning.ipynb` | Clean column names and fix column types |
| `03_processing_null_features.ipynb` | Remove columns with excessive null values |
| `04_data_cleaning_feature_construction.ipynb` | Construct response variable, convert binary types, standardize treatment names |
| `05_colinearity_analysis.ipynb` | Identify and visualize multicollinearity using pairwise correlations and VIF scores |
| `06_broad_cleaning.ipynb` | Standardize binary encodings, map categorical variables, numeric casting, label encoding |

---

### `notebooks/clinical_insights/` — Clinical Analysis

| Notebook | Description |
|----------|-------------|
| `01_baseline_characteristics.ipynb` | Compare baseline demographics and comorbidities across risk status, ADT, and NHT groups |
| `02_Time_to_NHT_Analysis.ipynb` | Analyze time from ADT start to NHT initiation across treatment combinations |
| `03_ADT_Risk_Association.ipynb` | Test association between CV risk and ADT/NHT agent using chi-square and Fisher's exact tests |
| `04_hx_htn_provider_bias.ipynb` | Investigate hypertension history and treatment selection patterns |
| `05_bp_meds.ipynb` | Test independence of NHT choice and prior BP medication use |
| `06_hld_history.ipynb` | Examine relationship between baseline hyperlipidemia and post-NHT lipid treatment |
| `07_DM_Meds_Start.ipynb` | Identify predictors of post-NHT diabetes medication initiation |
| `08_Cardio_Meta_Meds.ipynb` | Test whether baseline cardiometabolic conditions predict post-NHT medication escalation |
| `09_Cardio_Referral_Gaps.ipynb` | Analyze cardiology utilization and referral patterns across the NHT care pathway |
| `10_cardio_risk_eda.ipynb` | Distributional visualizations of CV risk and NHT × characteristic significance tests |
| `nht_adt_choice.ipynb` | Multinomial logistic regression tests for differential NHT and ADT prescribing patterns |
| `pvalues.ipynb` | Aggregate and visualize significant vs. non-significant results across all statistical tests |

---

### `notebooks/models/` — Machine Learning & Statistical Models

| Notebook | Description |
|----------|-------------|
| `01_logistic_regression.ipynb` | L1 and L2 penalized logistic regression with 5-fold CV; compares performance and coefficients |
| `02_random_forest.ipynb` | Random Forest classifier with Gini and permutation feature importance |
| `03_GAM.ipynb` | Logistic GAM with spline terms; feature selection via partial R² |
| `04_gradient_boosting.ipynb` | XGBoost model with SHAP value extraction and visualization |
| `05_model_comparison.ipynb` | Aggregate performance metrics and feature importance across all four models |
| `06_risk_phenotype.ipynb` | Profile CV risk factors and build additive risk score from significant features |
| `07_elastic_net.ipynb` | Elastic net logistic regression for CV risk prediction; AUC, metrics, top predictors |
| `08_elastic_net.ipynb` | Elastic net for variable selection, refit with OLS for odds ratios, CIs, and p-values |
| `09_elastic_net_visuals.ipynb` | Final poster visualizations: provider choice, risk profiles, referral gaps |
| `model_demo.ipynb` | **Demo notebook** — elastic net CV risk prediction on sample data |

---

### `notebooks/Results/`
Pre-computed outputs and figures from each analysis, organized by method: `Collinearity/`, `risk_phenotype/`, `LogisticRegression/`, `RandomForest/`, `GAM/`, `GradientBoosting/`, `ModelComparison/`.