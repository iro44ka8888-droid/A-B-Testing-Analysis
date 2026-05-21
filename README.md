# A/B Testing Analysis

> Statistical analysis of A/B test results using Python — conversion metrics
> evaluation across 4 tests with z-test for proportions.
> Contributed as **Data Analyst** (SQL, BigQuery, Python, Tableau Public).

[![SQL](https://img.shields.io/badge/SQL-BigQuery-4285F4?logo=google-cloud&logoColor=white)](https://cloud.google.com/bigquery)
[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)](https://colab.research.google.com/drive/1bgEkGuOSo4znFhjnlCaIg6-2939B39QE#scrollTo=RgrAC1M4kfFm)
[![Tableau Public](https://img.shields.io/badge/Tableau-Public-E97627?logo=tableau&logoColor=white)](https://public.tableau.com/app/profile/iryna.savelieva/viz/ABtest_17532074898820/ABtest?publish=yes)
[![Google Sheets](https://img.shields.io/badge/Results-Google%20Sheets-34A853?logo=google-sheets&logoColor=white)](https://docs.google.com/spreadsheets/d/1kawk4lMNMtAPBppOVknObBlY0HFqVt618a8DYT_pkk0/edit?gid=570772318#gid=570772318)

---

## Project Description

Statistical analysis of A/B test results for an e-commerce platform based on the
internal course database (data-analytics-mate, Google BigQuery). The project
automates statistical significance calculation using Python (z-test for proportions)
across 4 conversion metrics and 4 A/B tests, replacing manual online calculator workflows.

---

## Tools

- **SQL** (Google BigQuery) — data extraction with CTEs and UNION ALL
- **Python** (Google Colab) — statistical significance calculation
- **Pandas / NumPy** — data transformation and aggregation
- **Statsmodels** — z-test for proportions
- **Tableau Public** — interactive dashboard with conversion metrics
- **Google Sheets** — calculation results

---

## Metrics Analyzed

Each metric was calculated as: `event_count / sessions` for control (group 1) and test (group 2):

- `add_payment_info / session`
- `add_shipping_info / session`
- `begin_checkout / session`
- `new_account / session`

---

## Analysis Notebook

The full analysis is available in Google Colab:
[Open notebook →](YOUR_NOTEBOOK_LINK)

### Notebook structure

1. Database Connection — connecting to Google BigQuery (data-analytics-mate)
2. Data Extraction — SQL query with CTEs and UNION ALL to build the dataset
3. Statistical Significance Testing — z-test for proportions across 4 tests and 4 metrics
4. Calculation Results
5. Conclusions and Recommendations

---

## Key Findings

- **Test #4 is the most successful**: begin_checkout and new_account metrics both showed statistically significant improvements (p < 0.05) — recommended for full rollout
- **Test #1** improved middle-funnel metrics (add_payment_info, add_shipping_info, begin_checkout) but failed to increase new account creation
- **Test #2** showed no statistically significant changes across all metrics (p > 0.05) — not recommended for implementation
- **Test #3** affected only begin_checkout (p = 0.012) without improving the final conversion goal — new account creation

---

## Recommendations

1. Implement changes from **Test #4** — statistically confirmed improvement in both checkout and account creation
2. Do **not** implement **Test #2** results — no measurable effect on user behavior
3. Investigate why middle-funnel improvements in **Tests #1 and #3** did not convert into new registrations

---

## Links

- [Tableau Dashboard](https://public.tableau.com/app/profile/iryna.savelieva/viz/ABtest_17532074898820/ABtest?publish=yes) — interactive A/B test visualization
- [Calculation Results](https://docs.google.com/spreadsheets/d/1kawk4lMNMtAPBppOVknObBlY0HFqVt618a8DYT_pkk0/edit?gid=570772318#gid=570772318) — Google Sheets
- [Analysis Notebook](https://colab.research.google.com/drive/1bgEkGuOSo4znFhjnlCaIg6-2939B39QE#scrollTo=RgrAC1M4kfFm) — Google Colab
