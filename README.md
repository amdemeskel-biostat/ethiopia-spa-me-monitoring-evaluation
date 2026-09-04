# Health Facility Performance, Service Readiness, and Equity in Maternal and Child Health Service Delivery in Ethiopia

### An M&E Analysis of the Ethiopia Service Provision Assessment (SPA) 2021–22

## 📌 Project Overview

Health facilities may report offering a service without having all the basic infrastructure, equipment, supplies, and guidelines required to deliver that service consistently.

This project uses the **Ethiopia Service Provision Assessment (SPA) 2021–22** to examine this distinction by separately assessing:

* **Service availability** — whether a facility offers a service
* **Service readiness** — whether facilities offering the service have selected essential readiness components
* **Equity** — how readiness varies across regions, residence, facility groups, and managing authority
* **Readiness bottlenecks** — which essential components are most frequently missing

The analysis focuses on three maternal and child health service domains:

1. Antenatal Care (ANC)
2. Normal Delivery
3. Child Health

The overall objective was to demonstrate how facility-level health data can be transformed into practical **Monitoring & Evaluation (M&E) indicators** that support performance assessment, equity monitoring, and programmatic decision-making.

---

## 🎯 Objectives

The project aimed to:

1. Quantify national service availability for ANC, normal delivery, and child-health services.
2. Estimate facility-level service readiness using selected observable tracer components.
3. Assess readiness inequalities across:

   * Region
   * Urban/rural residence
   * Facility group
   * Managing authority
4. Identify component-level readiness bottlenecks.
5. Translate findings into M&E priorities and programmatic recommendations.

---

## 📊 Data Source

**Dataset:** Ethiopia Service Provision Assessment (SPA) 2021–22

* **Facilities originally sampled:** 1,407
* **Facilities included in the analytical dataset:** 1,158
* Facilities with zero or missing analytical weights were excluded.
* The SPA used a stratified design involving region and facility type.
* Analysis weights were derived from `v005 / 1,000,000` and used as normalized relative survey weights.

> **Important:** The raw SPA microdata are not included in this repository because the dataset is subject to data-access and redistribution restrictions.

---

## 🔬 Analytical Approach

All analyses were conducted in **R/RStudio**.

### Service Availability

Service availability was estimated as a **survey-weighted proportion** of eligible facilities reporting that they offered each service.

Normal-delivery availability used the eligible-facility denominator excluding health posts, consistent with the official SPA approach.

### Service Readiness

Facility-level readiness scores were constructed from selected observable tracer components.

The readiness score represents the percentage of selected components available at a facility. National readiness estimates were summarized using survey-weighted means.

**ANC readiness components:**

* Privacy
* Running water

**Normal delivery readiness components:**

* Privacy
* Running water
* Soap
* Gloves
* Suture
* Scissors
* Delivery pack
* Cord clamp
* Delivery bed

**Child-health readiness components:**

* Privacy
* Running water
* Soap
* Infant scale
* Scale
* Thermometer
* Stethoscope
* IMNCI guideline
* IMNCI chart

For child-health readiness, facilities were included when at least **7 of the 9 components (≥75%)** were assessed.

> **Important methodological note:** These readiness indices were constructed specifically for this portfolio project from selected tracer components. They are **not official SPA/SARA readiness indices**.

### Equity Analysis

Readiness was compared across:

* Region
* Urban/rural residence
* Facility group
* Managing authority

Equity gaps were calculated as:

**Highest weighted readiness − Lowest weighted readiness**

### Bottleneck Analysis

The weighted availability of individual readiness components was examined to identify commonly missing infrastructure, supplies, equipment, and guidelines.

No regression modeling, hypothesis testing, or causal analysis was performed.

---

## 📈 Key Findings

| Service domain  | Availability | Readiness |
| --------------- | -----------: | --------: |
| ANC             |    **74.7%** | **61.2%** |
| Normal Delivery |   **53.5%*** | **87.1%** |
| Child Health    |    **89.7%** | **66.6%** |

* Normal-delivery availability is calculated among eligible facilities excluding health posts.

### Major findings

* **ANC:** Relatively high availability but comparatively low readiness, with substantial equity disparities.
* **Normal delivery:** Lowest service availability but highest readiness among facilities offering the service.
* **Child health:** Very high availability but moderate readiness, demonstrating that service availability alone does not necessarily indicate adequate preparedness.
* **ANC had the largest regional readiness gap:** **47.8 percentage points**, ranging from 94.9% in Addis Ababa to 47.1% in Gambella.
* **Running water** was a recurring readiness bottleneck across the three service domains.
* **Soap** was also a major bottleneck in delivery and child-health readiness.
* Child-health readiness showed a particularly notable facility-type gap of **22.0 percentage points**.

---

## 🧭 M&E Framework

The project follows a simple performance-monitoring logic:

**Inputs → Service Availability → Service Readiness → Equity → Program Action**

This framework highlights why monitoring whether a facility offers a service should be complemented by monitoring whether the facility is adequately prepared to provide it.

---

## 💡 M&E Implications

The findings suggest several areas for programmatic attention:

1. Track **service availability and readiness as complementary indicators**.
2. Prioritize basic WASH infrastructure, particularly running water and soap.
3. Target low-readiness regions and facility groups.
4. Use facility-type-specific strategies rather than relying exclusively on national averages.
5. Incorporate readiness and equity measures into routine monitoring and dashboard systems.
6. Repeat readiness assessments periodically to monitor improvement, deterioration, and persistent bottlenecks.

These are **programmatic priorities suggested by the descriptive findings**, not causal claims about intervention effectiveness.

---

## 📉 Limitations

* The analysis is cross-sectional and cannot establish causality or changes over time.
* Readiness indices are portfolio-specific constructions rather than official SPA readiness measures.
* The ANC readiness index contains only two components.
* Delivery availability and readiness are based on related but distinct analytical populations.
* Some delivery facility-group subgroups are very small, particularly Health Posts and Clinics.
* Facility-level readiness does not directly measure patient-level quality of care or health outcomes.
* 249 facilities with zero or missing analytical weights were excluded.
* The analysis is descriptive and does not include regression or statistical significance testing.

---

## 🛠️ Tools & Skills Demonstrated

### Technical

* R
* RStudio
* `tidyverse`
* `haven`
* `labelled`
* `ggplot2`
* Survey-weighted analysis
* Data cleaning and transformation
* Indicator construction
* Missing-data handling
* Data visualization

### Public Health & M&E

* Health facility performance assessment
* Service availability measurement
* Service readiness assessment
* Equity analysis
* Bottleneck identification
* M&E indicator development
* Health-system performance interpretation
* Programmatic recommendations

---

## 📁 Repository Structure

```text
ethiopia-spa-me-monitoring-evaluation/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── report/
│   └── Ethiopia_SPA_2021_22_M&E_Portfolio_Report.pdf
│
├── figures/
│   ├── Figure_1_Service_Availability_and_Readiness.png
│   ├── Figure_2_Regional_Equity_in_Service_Readiness.png
│   └── Figure_3_Service_Readiness_Component_Availability.png
│
├── scripts/
│   ├── 01_data_import_cleaning.R
│   ├── 02_survey_weighting.R
│   ├── 03_indicator_construction.R
│   ├── 04_national_performance.R
│   ├── 05_equity_analysis.R
│   ├── 06_bottleneck_analysis.R
│   └── 07_figures.R
│
├── outputs/
│   ├── national_results.csv
│   ├── equity_results.csv
│   └── bottleneck_results.csv
│
└── docs/
    ├── methodology.md
    └── data_dictionary.md
```

---

## 🔐 Data Availability

The original SPA microdata are **not included in this repository**.

The repository contains the analytical code, documentation, figures, and selected derived outputs that can be shared without redistributing restricted microdata.

Users who wish to reproduce the analysis should obtain the SPA dataset through the appropriate official data-access process.

---

## 📄 Project Report

The complete portfolio report is available in:

`report/Ethiopia_SPA_2021_22_M&E_Portfolio_Report.pdf`

---

## 👤 Author

**Amdemeskel Mulugeta**

MPH Biostatistics | Public Health Researcher | Health Data Analyst

**Areas of interest:**
Biostatistics • Public Health Research • Health Data Analytics • Monitoring & Evaluation • Global Health

