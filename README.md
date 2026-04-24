#  Delhivery — Feature Engineering & Hypothesis Testing

> A comprehensive business case study transforming raw logistics data into a feature-engineered, model-ready dataset through statistical analysis and hypothesis testing.

**By: Karan Agarwal**

---

## 📌 Project Overview

Delhivery is India's largest and fastest-growing fully integrated logistics services provider (by revenue, FY2021), operating across 18,850+ pin codes with services spanning express parcel, PTL/FTL freight, cross-border logistics, and supply chain solutions.

This project addresses a core operational analytics problem: **raw logistics data is stored at segment-level granularity**, making it difficult to assess trip-level efficiency and reliability. The goal is to clean, transform, aggregate, and engineer this data into structured trip-level features suitable for operational analysis and predictive modeling.

---

## 🎯 Problem Statement

> Transform segment-level delivery data into structured, meaningful trip-level features that can be used for operational performance analysis and predictive modeling.

**Key questions addressed:**
- Are OSRM-based predicted time and distance reliable indicators of actual trip performance?
- Is there consistency between aggregated trip-level metrics and segment-level metrics?
- Are there identifiable operational inefficiencies across routes and corridors?

---

## 🗂️ Repository Structure

```
Delhivery_Feature_Engineering/
│
├── Notebook/
│   └── Delhivery_Feature_Engineering.ipynb   # Main analysis notebook
│
├── Report/
│   └── Delhivery_Feature_Engineering.pdf     # Full project report
│
├── requirements.txt                           # Python dependencies
├── .gitignore                                 # Files excluded from version control
└── README.md                                  # This file
```
---

## 📊 Analysis Sections

| # | Section | Description |
|---|---------|-------------|
| 1 | Introduction & Problem Statement | Business context, objectives, scope |
| 2 | Dataset Overview & Basic Metrics | Shape, types, initial exploration |
| 3 | Data Cleaning & Preprocessing | Missing values, duplicates, type fixes, validation |
| 4 | Statistical Summary & Distribution | Descriptive stats, histograms, boxplots, IQR |
| 5 | Row Merging & Aggregation | Segment → Trip level aggregation pipeline |
| 6 | Feature Engineering | Temporal features, location features, new derived columns |
| 7 | Exploratory Data Analysis | Patterns, distributions, route analysis |
| 8 | Hypothesis Testing | Two-Sample T-Test, ANOVA, Chi-Square tests |
| 9 | Outlier Detection & Treatment | IQR-based detection and capping |
| 10 | Encoding Categorical Variables | One-Hot Encoding |
| 11 | Feature Scaling | Standardization / Normalization |
| 12 | Business Insights | Interpreted statistical findings |
| 13 | Recommendations | Actionable operational improvements |
| 14 | Conclusion & Key Takeaways | Summary of findings |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| `Python 3.x` | Core programming language |
| `Pandas` | Data manipulation & aggregation |
| `NumPy` | Numerical operations |
| `Matplotlib` | Data visualization |
| `Seaborn` | Statistical plots |
| `SciPy (stats)` | Hypothesis testing (T-Test, ANOVA, Chi-Square) |
| `Jupyter Notebook` | Interactive analysis environment |

---

## 📂 Dataset

The dataset contains raw logistics data extracted from Delhivery's data engineering pipelines, stored at **segment-level granularity**.

**Key columns include:**
- `trip_uuid` — Unique trip identifier
- `route_type` — FTL (Full Truck Load) or Carting
- `trip_creation_time` — Timestamp of trip creation
- `source_center` / `destination_center` — Origin and destination hubs
- `actual_time` / `osrm_time` — Actual vs. OSRM-predicted time
- `actual_distance_to_destination` / `osrm_distance` — Actual vs. predicted distance
- `segment_actual_time`, `segment_osrm_time` — Segment-level time metrics

> **Note:** The raw dataset (`delhivery_data.csv`) is not included in this repository due to size constraints. You can find it on [Kaggle](https://www.kaggle.com/datasets/dakshmiglani/delhivery-feature-engineering).

---

## 📈 Key Findings

- **OSRM predictions** show statistically significant discrepancies from actual trip times and distances, indicating model recalibration is needed for Indian road conditions.
- **FTL trips** exhibit different delay patterns compared to Carting trips, warranting separate operational benchmarks.
- **Aggregation pipeline** successfully reduced segment-level rows to clean trip-level records, preserving cumulative metrics while summing partial ones.
- **Temporal features** (hour of day, day of week, month) reveal clear operational patterns in trip frequency and delay likelihood.
- **Outlier treatment** via IQR capping retained distribution shape while mitigating the effect of extreme anomalies.

---

## 💡 Business Impact

The insights from this analysis can help Delhivery:
- 🗺️ Improve route planning efficiency
- ⚠️ Identify high-delay corridors for targeted intervention
- 📐 Measure and improve OSRM prediction accuracy
- ⏱️ Reduce delivery time variability
- 🚛 Optimize transportation mode selection (FTL vs. Carting)
- 🔮 Strengthen logistics forecasting capabilities

---

## ⚙️ Setup & Usage

### 1. Clone the repository
```bash
git clone https://github.com/Karan-Agarwal94/Delhivery_Feature_Engineering.git
cd Delhivery_Feature_Engineering
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Launch the notebook
```bash
jupyter notebook Notebook/Delhivery_Feature_Engineering.ipynb
```

---

## 👤 Author

**Karan Agarwal**  
GitHub: [@Karan-Agarwal94](https://github.com/Karan-Agarwal94)

---

## 📄 License

This project is for educational and portfolio purposes. The analysis methodology and code are original work by the author.