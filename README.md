# 🦠 Covid-19 Global Analysis

![Python](https://img.shields.io/badge/Python-3.7+-blue?style=flat-square&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data_Wrangling-green?style=flat-square&logo=pandas)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualisation-orange?style=flat-square)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-red?style=flat-square&logo=jupyter)
![World Bank](https://img.shields.io/badge/World_Bank-Socioeconomic_Data-purple?style=flat-square)
![Johns Hopkins](https://img.shields.io/badge/Data-Johns_Hopkins_CSSE-lightgrey?style=flat-square)

> **A full-pipeline Python data analytics project** that downloads, processes, and visualises global COVID-19 case data — enriched with World Bank socioeconomic indicators to uncover patterns in mortality, spread, and healthcare capacity across countries and continents.

---

## 🗺️ Pipeline at a Glance

```
Download Raw Data  →  Feature Engineering  →  Data Processing  →  Notebooks  →  Visualisations
   (3 sources)         (10 modules)            (12 datasets)       (5 topics)     (Matplotlib)
```

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| **Language** | Python 3.7+ |
| **Data Manipulation** | Pandas, NumPy |
| **Visualisation** | Matplotlib, SciPy |
| **Data Sources** | Johns Hopkins CSSE (via Git), World Bank API (`wbdata`), DataHub.io |
| **Notebooks** | Jupyter Notebook |
| **Version Control** | GitPython (`gitpython`) |
| **Testing** | unittest |

---

## 📂 Project Structure

```
COVID19/
│
├── data/
│   ├── download_data.py          # Auto-downloads all 3 data sources
│   └── processed/                # Output of feature engineering scripts
│
├── features/
│   ├── make_all.py               # Master script — runs full pipeline
│   ├── make_cases.py             # Confirmed / Recovered / Dead / Active cases
│   ├── make_cases_daily_change.py # Day-over-day case delta
│   ├── make_cases_since_t0.py    # Cases normalized from outbreak start (t=0)
│   ├── make_continents.py        # Continent-level aggregations
│   ├── make_coordinates.py       # Country lat/lon for map plots
│   ├── make_country_stats.py     # Per-country summary stats
│   ├── make_country_to_continent.py  # Country → Continent mapping
│   ├── make_mortality.py         # Mortality rate (deaths / confirmed × 100)
│   ├── make_world_bank.py        # Merge COVID data with World Bank indicators
│   └── utils.py                  # Shared helpers
│
├── notebooks/
│   ├── Data-wrangling.ipynb                    # Raw → clean data walkthrough
│   ├── Exploratory-analysis-globally.ipynb     # Global trends & continent breakdown
│   ├── Exploratory-analysis-mortality.ipynb    # Mortality rate deep-dive
│   ├── Exploratory_analysis_fancy_plot.ipynb   # Advanced custom visualisations
│   └── Exploratory_analysis_socioeconomic.ipynb # GDP, health spend, life expectancy vs COVID
│
├── visualizations/
│   └── covid_data_viz.py         # CovidDataViz class — reusable plotting API
│
└── tests/
    └── test.py                   # Unit tests for data integrity
```

---

## ⚙️ Setup & Installation

### Step 1 — Clone the Repository
```bash
git clone https://github.com/your-username/Covid19Analysis.git
cd Covid19Analysis/Data-Analytics-Projects-in-python-main/COVID19
```

### Step 2 — Install Dependencies
```bash
pip install pandas numpy matplotlib scipy requests gitpython wbdata jupyter
```

### Step 3 — Download Raw Data
```bash
python data/download_data.py
```
This automatically pulls:
- **Johns Hopkins CSSE** COVID-19 time series (via `git clone`)
- **DataHub.io** country/continent mapping CSV
- **World Bank API** — 7 socioeconomic indicators per country

### Step 4 — Run Feature Engineering
```bash
cd features/
python make_all.py
```
Generates 12 processed `.csv` datasets in `data/processed/`.

### Step 5 — Launch Notebooks
```bash
jupyter notebook notebooks/
```

---

## 📊 Datasets Generated

| Dataset | Description |
|---------|-------------|
| `confirmed_cases.csv` | Daily cumulative confirmed cases by country |
| `recovered_cases.csv` | Daily cumulative recovered cases by country |
| `dead_cases.csv` | Daily cumulative deaths by country |
| `active_cases.csv` | Active = Confirmed − Recovered − Dead |
| `confirmed_cases_daily_change.csv` | Day-over-day new case count |
| `confirmed_cases_since_t0.csv` | Cases normalized from outbreak day (t=0) |
| `mortality_rate.csv` | `(Deaths / Confirmed) × 100` per country over time |
| `continents.csv` | Continent-level aggregated case data |
| `country_to_continent.csv` | Country → Continent lookup |
| `coordinates.csv` | Lat/Lon per country for map plots |
| `country_stats.csv` | Peak cases, total deaths, max mortality per country |
| `world_bank.csv` | COVID data merged with GDP, population, life expectancy etc. |

---

## 🌍 World Bank Indicators Integrated

| Indicator Code | Description |
|----------------|-------------|
| `NY.GDP.PCAP.PP.CD` | GDP per capita, PPP (current international $) |
| `SP.POP.TOTL` | Total population |
| `SP.URB.TOTL.IN.ZS` | Urban population (% of total) |
| `SP.DYN.LE00.IN` | Life expectancy at birth (years) |
| `SH.XPD.CHEX.GD.ZS` | Current health expenditure (% of GDP) |
| `EN.POP.SLUM.UR.ZS` | Slum population (% of urban) |
| `SP.RUR.TOTL.ZS` | Rural population (% of total) |

---

## 📓 Notebooks Overview

### 1. `Data-wrangling.ipynb`
Raw data ingestion and cleaning — pivoting time series, removing cruise ships (Diamond Princess, MS Zaandam), country renaming, and type enforcement.

### 2. `Exploratory-analysis-globally.ipynb`
Global case trends, continent-level breakdowns, top affected countries, and cumulative vs daily new case plots.

### 3. `Exploratory-analysis-mortality.ipynb`
Country-level mortality rate analysis (`Deaths / Confirmed × 100`), highest mortality countries, and time-series mortality curves.

### 4. `Exploratory_analysis_fancy_plot.ipynb`
Advanced, publication-quality visualisations — custom styled multi-panel charts and annotated trend lines.

### 5. `Exploratory_analysis_socioeconomic.ipynb`
Correlates COVID outcomes (mortality, case growth) with World Bank indicators — GDP, health expenditure, life expectancy, urbanisation — using scatter plots and regression analysis.

---

## 📈 Key Analyses Performed

- ✦ **Global spread timeline** — confirmed, active, recovered, and dead cases over time
- ✦ **Daily new cases** — day-over-day delta to identify outbreak peaks
- ✦ **Outbreak comparison (t=0)** — country trajectories aligned from first case
- ✦ **Mortality rate trends** — `deaths / confirmed` per country, per day
- ✦ **Top 10 highest mortality countries** — ranked and visualised
- ✦ **Continent-level aggregation** — Asia, Europe, Americas, Africa, Oceania
- ✦ **Socioeconomic correlations** — does GDP or health spending correlate with lower mortality?
- ✦ **Regression analysis** — linear trend fitting with `scipy.stats.linregress`

---

## 🧪 Data Quality & Testing

```bash
cd tests/
python -m unittest test.py
```

Tests verify:
- Cruise ships (`Diamond Princess`, `MS Zaandam`) excluded from all datasets
- Data integrity across confirmed, recovered, dead, and active case files
- Country naming consistency across all processed CSVs

---

## 📦 `CovidDataViz` — Reusable Visualisation Class

```python
from visualizations.covid_data_viz import CovidDataViz

viz = CovidDataViz(path='./data/processed')

# Get country time series
ts = viz.get_country_ts('India')

# List countries with highest mortality
top_mortality = viz.list_highest_mortality(n=10)

# Get continent-level trends
continent_ts = viz.get_continent_ts('Europe')
```

---

## 🚀 Learning Outcomes

By completing this project, you gain hands-on experience with:

- [x] Automated data collection from GitHub, REST APIs, and World Bank
- [x] Real-world data cleaning — reshaping, renaming, type conversion
- [x] Feature engineering — mortality rates, daily deltas, t=0 normalization
- [x] Exploratory Data Analysis (EDA) with Pandas & Matplotlib
- [x] Socioeconomic correlation analysis with SciPy regression
- [x] Modular Python project structure with reusable class-based visualisations
- [x] Writing unit tests for data pipeline integrity

---

## 📌 Conclusion

This project delivers a **production-grade Python analytics pipeline** on one of the most impactful datasets of the 21st century. It goes beyond basic charting — combining multi-source data ingestion, automated feature engineering, and socioeconomic enrichment to answer real-world questions about how COVID-19 spread and why outcomes varied so dramatically across countries.

---

*Data Sources: Johns Hopkins CSSE · World Bank Open Data · DataHub.io*  
*Built with Python · Pandas · Matplotlib · SciPy · Jupyter*
