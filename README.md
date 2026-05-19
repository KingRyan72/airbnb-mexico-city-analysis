# Airbnb Mexico City — Price Analysis

> **What factors determine the nightly price of an Airbnb listing in Mexico City, and what can they tell us about investment opportunities?**

A statistical analysis of 20,000+ active Airbnb listings in Mexico City using real data from [Inside Airbnb](https://insideairbnb.com/get-the-data/). This project applies exploratory data analysis, hypothesis testing, and regression modeling to understand the drivers of short-term rental pricing.

---

## Project Structure

```
airbnb-mexico-city-analysis/
│
├── 01_data_loading.ipynb       # Download, load, and first inspection
├── 02_data_cleaning.ipynb      # Cleaning, parsing, and feature engineering
├── 03_eda_statistics.ipynb     # Exploratory analysis and hypothesis testing
├── 04_regression_model.ipynb   # Explanatory regression model
│
├── data/                       # Not tracked by git — generated on first run
│   ├── raw/                    # Original files from Inside Airbnb
│   └── processed/              # Cleaned datasets ready for analysis
│
├── reports/
│   └── figures/                # Saved charts and visualizations
│
├── requirements.txt
└── README.md
```

---

## Key Questions

- Which features have the strongest statistical relationship with price?
- Do prices differ significantly across neighbourhoods? (Kruskal-Wallis)
- How much does each additional bedroom, bathroom, or amenity add to the price?
- Which areas are underpriced relative to their characteristics — a signal for investors?

---

## Methods

| Phase | Techniques |
|---|---|
| Data acquisition | `requests`, Inside Airbnb |
| Cleaning | Regex parsing, IQR outlier filtering, median imputation |
| EDA | Descriptive statistics, confidence intervals, distribution analysis |
| Hypothesis testing | Kruskal-Wallis, Mann-Whitney U, bootstrapped CIs |
| Modeling | Multiple linear regression, log-price transformation, VIF diagnostics |
| Comparison | Random Forest for feature importance cross-validation |

---

## Key Results

- **20,329 clean listings** retained after cleaning (75.2% of original dataset)
- **`accommodates`** is the strongest continuous predictor of price (r = 0.455)
- **Room type** has a statistically significant effect on price (Kruskal-Wallis p < 0.05)
- **Superhost premium** confirmed — $1,050 vs $907 MXN median (~16% more)
- **OLS model R²** explains a meaningful share of price variance with interpretable coefficients

---

## Tech Stack

- **Python 3.11** — pandas, numpy, matplotlib, seaborn, scikit-learn, scipy, statsmodels
- **Jupyter Notebooks** — one notebook per phase for full reproducibility
- **Data source:** Inside Airbnb — Mexico City (December 2024 scrape)

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/KingRyan72/airbnb-mexico-city-analysis.git
cd airbnb-mexico-city-analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run notebooks in order
jupyter notebook 01_data_loading.ipynb
```

> Notebook 01 downloads the dataset automatically from Inside Airbnb.
> If the URL is outdated, visit [insideairbnb.com/get-the-data](https://insideairbnb.com/get-the-data/)
> and update `SCRAPE_DATE` in the first code cell.

---

## Dataset

- **Source:** [Inside Airbnb](https://insideairbnb.com/) — publicly available, no login required
- **Coverage:** Mexico City, 27,051 raw listings → 20,329 after cleaning
- **Files used:** `listings.csv`, `calendar.csv`, `reviews.csv`
- **License:** [Creative Commons CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)

Raw data files are **not tracked by git**. Run Notebook 01 to download them automatically.

---

## Author

**Edgar A. Mercado Blanco**
Data Scientist | [LinkedIn](https://www.linkedin.com/in/edgar-mblanco/) | [Portfolio](https://github.com/KingRyan72)

*Certifications: Google Advanced Data Analytics · Azure Data Scientist Associate (DP-100) · Google Business Intelligence*