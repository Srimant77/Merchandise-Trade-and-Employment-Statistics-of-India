# Merchandise Trade and Employment Dynamics in India: An Analysis of E-Way Bill Data

**Author:** Srimant Mishra  

## Project Overview

This project analyzes the transformation of the Indian economy from a cash-based informal system to a formalized digital economy following the implementation of the **Goods and Services Tax (GST)** in 2016. Specifically, this study utilizes **E-Way Bill** data (electronic documentation for the movement of goods) to map the patterns of merchandise trade across Indian states from 2018 to present.

Crucially, this project integrates trade data with **employment statistics** to investigate correlations between economic formalization and labor market dynamics, with a specific focus on gender disparities and the distinction between casual and formal employment.

## Motivation

India has historically functioned as a cash-heavy, informal economy due to high tax rates and compliance burdens. The 2016 GST implementation introduced incentives (input tax credits) and structural pressures that accelerated formalization. A key component of this shift was the **E-Way Bill**, a unique 12-digit digital record required for moving goods valued over ₹50,000.

This project was motivated by:
1.  **Novelty:** The E-Way bill dataset provides a relatively new, high-frequency lens to view economic activity that has been largely unexplored outside of government or journalistic circles.
2.  **Economic Geography:** To verify if economic activity is concentrating in specific regions (North vs. South / East vs. West).
3.  **Socio-Economic Linkages:** To understand if the rise in merchandise trade translates to better quality (formal) jobs for men and women.

## Data Description

The analysis relies on two primary datasets released under the **Government Open Data License (GODL)**.

### 1. E-Way Bill Data
* **Scope:** Merchandise trade movement above ₹50,000 threshold.
* **Timeframe:** 2018 – 2025.
* **Granularity:** Segregated by Year, Month, and State.
* **Metrics:**
    * **Volume:** Number of bills generated.
    * **Value:** Aggregate assessable value of goods.
    * **Flow:** Categorized into **Incoming**, **Outgoing**, and **Within-State** trade.

### 2. Employment Data
* **Timeframe:** 2017 – 2023.
* **Granularity:** State and Union Territory level.
* **Demographics:** Split by Gender (Men/Women) and Geography (Rural/Urban).
* **Categories Analyzed:**
    * **Casual Labour:** Irregular work, no benefits.
    * **Regular Wage/Salary:** Formal employment.

*Data Source:* https://ndap.niti.gov.in/

## Research Questions

1.  **Geographical Divides:** Is there a North-South or East-West divide in merchandise trade intensity?
2.  **Growth Trajectory:** What is the Compound Annual Growth Rate (CAGR) of trade across different states? Are specific regions lagging?
3.  **Formalization:** Is there evidence of increasing formalization via E-Way bill adoption?
4.  **Employment Correlation:**
    * Does rising trade reduce casual labor?
    * Does rising trade increase formal employment?
    * **Gender Dynamics:** How does the impact differ for men versus women?

## Methodology

* **Data Extraction & Cleaning:** Built a dictionary-based data structure to store state-level metrics (Count, Value, Trade Type) for easy retrieval.
* **Metric Calculation:**
    * Derived **Correlations**: Incoming vs. Outgoing, Internal vs. External, Value vs. Count.
    * Calculated **CAGR**: To smooth out volatility (including the Covid-19 shock) and measure long-term trends.
* **Geospatial Analysis:** Utilized **Geopandas** and an external **GeoJSON** file of Indian districts/states to superimpose trade data onto maps, allowing for the visualization of regional clusters.
* **Dashboarding:** Created a state-level dashboard to contextualize local metrics against national averages.

## Key Findings

### 1. Sustained Economic Growth
Despite the Covid-19 shock, merchandise trade has shown high momentum.
* **CAGR (Value):** 12.28% (Outpacing India's overall growth rate of ~5.5%).
* **CAGR (Count):** ~15% (Indicating higher adoption frequency for smaller transactions).

### 2. The West-East Divide
* **The West Dominates:** Maharashtra and Gujarat are the clear leaders, driven by ports and industrial hubs.
* **The South:** Tamil Nadu is a major manufacturing leader. Kerala, however, is an outlier—high social indicators but low merchandise trade output.
* **The East Lags:** Aside from West Bengal, the east sees lower activity. Surprisingly, the **Mineral Belt** (Odisha, Jharkhand, Chhattisgarh) shows low trade value despite high mining activity, suggesting structural issues.

### 3. Regional Growth Anomalies
* **Ladakh:** Highest growth (>30% CAGR), likely driven by infrastructure/military push and a low base effect.
* **Mizoram:** The only state showing stagnation, potentially due to exclusion from recent infrastructure projects in the North East.

### 4. Merchandise Trade vs. Casual Labor
* **General Trend:** Higher trade correlates with **lower** casual labor (more formalization).
* **Exceptions (Positive Correlation):**
    * **Mining States (East):** Reliance on contract labor for extraction.
    * **Rich Regions (Delhi/Goa):** High trade attracts migrant labor willing to take any available work.

### 5. The Gender Paradox in Formal Employment
* **Men:** Higher trade generally leads to **more formal jobs**.
* **Women:** Higher trade correlates with **fewer formal jobs** in most states.
    * *Observation:* This counter-intuitive trend holds across both industrialized and non-industrialized states.
    * *Geography:* A clear divide exists. States "below the line" (Southern/Western) show positive correlations, while the populous Northern/Eastern states show negative correlations for formal job creation.

## Implications

* **For Policymakers:** The analysis identifies a geographical line separating states creating formal jobs from those that are not. This offers a roadmap for targeted interventions in labor formalization and infrastructure to prevent bottlenecks.
* **For Businesses:** Provides a rubric for logistics planning—identifying which states have mature formal economies versus those reliant on volatile, casual labor markets.
* **For Journalists:** Highlights the disconnect between economic growth and female formal employment, as well as the migration patterns from "jobless growth" regions.

## Limitations

* **Threshold Bias:** E-Way bills only capture trade >₹50,000, potentially excluding the micro-economy.
* **Correlation vs. Causation:** While strong correlations exist between trade and employment, external factors (migration policies, local laws) play a role.
* **Data Lag:** Employment data reporting cycles may not perfectly align with real-time E-Way bill generation.

## License

This project utilizes data under the **Government Open Data License (GODL)**. The code and analysis within this repository are open for adaptation and use under the MIT License
