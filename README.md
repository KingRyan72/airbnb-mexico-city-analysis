# Airbnb Mexico City — Price Analysis

> **What factors determine the nightly price of an Airbnb listing in Mexico City, and what can they tell us about investment opportunities?**

A statistical analysis of 18,000+ active Airbnb listings in Mexico City using real data from [Inside Airbnb](https://insideairbnb.com/get-the-data/). This project applies exploratory data analysis, hypothesis testing, and regression modeling to understand the drivers of short-term rental pricing.

---

## Project Structure

```
airbnb-mexico-city-analysis/
│
├── data/
│   ├── raw/               # Original files from Inside Airbnb (not tracked by git)
│   └── processed/         # Cleaned datasets ready for analysis
│
├── notebooks/
│   ├── 01_data_loading.ipynb       # Download, load, and first inspection
│   ├── 02_data_cleaning.ipynb      # Cleaning, parsing, and feature engineering
│   ├── 03_eda_statistics.ipynb     # Exploratory analysis and hypothesis testing
│   └── 04_regression_model.ipynb   # Explanatory regression model
│
├── reports/
│   └── figures/           # Saved charts and visualizations
│
├── requirements.txt
└── README.md
```

---

## Key Questions

- Which features have the strongest statistical relationship with price?
- Do prices differ significantly across neighbourhoods? (ANOVA / Kruskal-Wallis)
- How much does each additional bedroom, bathroom, or amenity add to the price?
- Which areas are underpriced relative to their characteristics — a signal for investors?

---

## Methods

| Phase | Techniques |
|---|---|
| Data acquisition | `requests`, Inside Airbnb API |
| Cleaning | Regex parsing, IQR outlier filtering, median imputation |
| EDA | Descriptive statistics, confidence intervals, distribution analysis |
| Hypothesis testing | ANOVA, Kruskal-Wallis, Mann-Whitney U |
| Modeling | Multiple linear regression, log-price transformation, VIF diagnostics |
| Comparison | Random Forest for feature importance cross-validation |

---

## Tech Stack

- **Python 3.11** — pandas, numpy, matplotlib, seaborn, scikit-learn, scipy, statsmodels
- **Jupyter Notebooks** — one notebook per phase for reproducibility
- **Data source:** Inside Airbnb — Mexico City (scraped December 2024)

---

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/your-username/airbnb-mexico-city-analysis.git
cd airbnb-mexico-city-analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run notebooks in order
jupyter notebook notebooks/01_data_loading.ipynb
```

> The first notebook will automatically download the dataset from Inside Airbnb.  
> If the URL is outdated, visit [insideairbnb.com/get-the-data](https://insideairbnb.com/get-the-data/) and update `SCRAPE_DATE` in Notebook 01.

---

## Dataset

- **Source:** [Inside Airbnb](https://insideairbnb.com/) — publicly available, no login required
- **Coverage:** Mexico City, ~18,000+ active listings
- **Files used:** `listings.csv`, `calendar.csv`, `reviews.csv`
- **License:** [Creative Commons CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/)

The raw data files are **not tracked by git** (see `.gitignore`). Run Notebook 01 to download them automatically.

---

## Author

**[Your Name]**  
Data Scientist | [LinkedIn](https://linkedin.com/in/your-profile) | [Portfolio](https://your-portfolio.com)

*Certifications: Google Advanced Data Analytics · Azure Data Scientist Associate (DP-100) · Google Business Intelligence*
