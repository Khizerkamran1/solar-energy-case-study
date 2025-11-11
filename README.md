# Solar Energy Case Study — Barriers to Solar Energy Solution Adoption

## Overview
This repository contains the full analytical workflow, visualizations, and findings from a data-driven case study evaluating **barriers to national solar energy adoption**.  
The analysis integrates quantitative energy indicators with qualitative policy and socio-economic metrics to identify the most impactful drivers of solar deployment worldwide.

The project applies both **statistical** and **machine learning** approaches to validate the influence of various policy, infrastructure, and market barriers using global renewable energy datasets.

## Objectives
1. Quantify which policy, financial, infrastructural, and demographic barriers most influence national solar capacity.  
2. Validate statistical significance through correlation analysis and machine learning models.  
3. Compare impacts across major barrier categories:
   - **Resource-based barriers**  
   - **Regional/institutional barriers**  
   - **Demographic barriers**  
   - **Other systemic barriers**
4. Generate insights for **policy intervention** and **investment prioritization** in solar energy infrastructure.

## Datasets Used
The analysis utilizes **publicly available, high-quality energy datasets** from reputable global organizations:

| Dataset | Description | Source |
|----------|--------------|--------|
| **installed-solar-pv-capacity.csv** | Country-level cumulative installed solar photovoltaic (PV) capacity (in GW). Used as the dependent variable (`Solar_Capacity_GW_log`). | [Our World in Data (2024)](https://ourworldindata.org/energy) |
| **cost-of-energy.csv** | Levelized cost of electricity (LCOE) across major renewable energy technologies (USD/kWh). Replaced the previous `data_08` file and used as the cost-efficiency indicator for solar energy competitiveness. | [Our World in Data (2024)](https://ourworldindata.org/energy) |
| **RISE 2016 — Regulatory Indicators for Sustainable Energy** | Comprehensive country-level metrics on energy policy frameworks, financing mechanisms, and infrastructure readiness. Serves as the foundation for policy and indicator-level analysis. | [World Bank EnergyData.info (2016)](https://energydata.info/dataset/world-regulatory-indicators-for-sustainable-energy-2016) |

## Methodology

### 1. Data Integration and Cleaning
- Merged multi-source datasets using `Country` and `Year` as key identifiers.  
- Log-transformed the dependent variable (`Solar_Capacity_GW`) to normalize skewed distributions.  
- Removed redundant or incomplete indicators for model efficiency.

### 2. Exploratory Data Analysis (EDA)
- Computed **Spearman correlation coefficients** between each policy or technical indicator and solar capacity.  
- Visualized results by **major barrier categories** using grouped horizontal bar plots.  
- Identified that **resource-related** and **policy-enabling** variables showed the strongest positive associations.

### 3. Machine Learning Validation
Implemented a **Random Forest Regressor** to validate predictive accuracy of the correlation insights:
- Excluded dependent variables and non-predictive identifiers.  
- Split data into training and testing sets (80/20).  
- Achieved moderate predictive accuracy (`R² ≈ 0.49`) and low mean absolute error (`MAE ≈ 0.48`).  
- Determined **top predictors** of solar capacity:
  - Renewable Energy Score  
  - Energy Efficiency Score  
  - LCOE of Solar and Onshore Wind  
  - Financing Mechanisms for Energy Efficiency  

Feature importance and permutation sensitivity were aggregated across barrier types to measure **predictive stability**, confirming that **resource-based factors** remain the most influential.

## Key Findings
- **Resource-based barriers** (e.g., renewable energy scoring, energy efficiency, cost competitiveness) are the dominant drivers of solar adoption.  
- **Regional and demographic barriers** (e.g., affordability, creditworthiness, policy inconsistency) exhibit higher uncertainty, suggesting these areas require **context-sensitive** and **adaptive policy design**.  
- Countries with consistent energy pricing, monitoring frameworks, and renewable integration planning show stronger solar deployment outcomes.  
- Machine learning verification reinforced statistical results, confirming that policy and cost-related indicators substantially explain solar adoption variance.

## Defensible Assumptions
1. Missing indicator values were assumed to represent unavailable or non-applicable policy data, not zero performance.  
2. The **log transformation** of `Solar_Capacity_GW` was appropriate to stabilize variance in highly skewed energy data.  
3. The **Spearman correlation** was chosen due to its robustness against non-linear relationships in socio-technical indicators.  
4. Random Forest was used for interpretability and feature ranking rather than forecasting.  
5. The RISE dataset’s most recent comprehensive year (2016) was considered representative of policy baselines for the decade-long trend.

## Policy Implications
- Policymakers should focus on **lowering capital costs** and **stabilizing energy pricing mechanisms** to enhance renewable competitiveness.  
- **Feed-in tariffs, efficiency standards, and carbon pricing** frameworks remain essential levers for accelerating national adoption rates.  
- Expanding **credit access** and **regulatory incentives** can reduce demographic constraints in emerging markets.  
- Governments should pair **technical expansion** with **institutional strengthening** to ensure long-term deployment sustainability.

## References
All references, datasets, and articles used are cited in APA 6th Edition within the report.  

A complete list is included at the end of the Jupyter Notebook under **Bibliography (APA 6th Edition)**.

## Author
**Khizer Kamran**  
*University of Calgary — Data Science and Machine-learning (MDSA)*

GitHub Repository: [https://github.com/Khizerkamran1/solar-energy-case-study](https://github.com/Khizerkamran1/solar-energy-case-study)

