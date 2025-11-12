# S&P 500 Trends Analysis Project - Data Preprocessing & Crawling

## Project Overview

Data preprocessing and crawling work was performed to integrate the S&P 500 index with various economic indicators for analysis.

---

## 1. Data Crawling

Three economic indicators were crawled from websites: CPI (Consumer Price Index), VIX (Volatility Index), and UNEMPLOYMENT RATE. CPI and UNEMPLOYMENT RATE were collected as monthly data, while VIX was collected as daily data and later aggregated to monthly averages.

---

## 2. Data Preprocessing and Merging

Date format conversion, numeric conversion, and year/month aggregation were performed on the collected data. Column names were standardized: `CPIAUCSL` → `CPI`, `UNRATE` → `UNEMPLOYMENT RATE`, `VIXCLS` → `VIX`. The data was merged with existing datasets (S&P 500, GPR, GDP, Federal Funds Rate) to create two datasets: monthly (`merged_monthly_df`) and yearly (`merged_yearly_df`).

---

## 3. Missing Value (NaN) Handling

Missing value analysis revealed that the VIX column had the most NaN values (12.24% monthly, 12.5% yearly). Since VIX data starts from 1990, earlier periods have no data. To minimize data loss, only rows with NaN in VIX were selectively removed, creating `merged_monthly_df_clean` and `merged_yearly_df_clean` datasets.

---

## 4. Feature Engineering

CHANGE RATE columns were created for each economic indicator to show percentage change from the previous period. Each original column is followed by its corresponding CHANGE RATE column, with monthly data showing month-over-month changes and yearly data showing year-over-year changes. This resulted in four datasets: `merged_monthly_df_with_changes`, `merged_yearly_df_with_changes`, `merged_monthly_df_clean_with_changes`, and `merged_yearly_df_clean_with_changes`.

---

## 5. Generated Datasets

A total of 8 datasets were created: 2 original datasets (monthly, yearly), 2 cleaned datasets (NaN removed), and 4 datasets with CHANGE RATE columns.

---

## 6. Data Visualization

All economic indicators were normalized to a 0-1 scale for comparison in a single graph. Normalized graphs were created for both the original monthly data and the NaN-cleaned data, with legends placed outside the graph on the right side.

---

## 7. Key Achievements

Successfully integrated 7 economic indicators and built analyzable datasets through systematic preprocessing and feature engineering. CHANGE RATE columns enable easy identification of trends in each indicator, and normalized graphs allow for multi-indicator comparison.

## Resources

CPI : https://fred.stlouisfed.org/series/CPIAUCSL
VIX : https://fred.stlouisfed.org/series/VIXCLS
Unemployment rate : https://fred.stlouisfed.org/series/UNRATE

*FYI, CPI (databases) : https://www.bls.gov/cpi/data.htm
