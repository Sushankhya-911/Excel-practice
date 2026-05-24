# Nepal Economy Dataset — README

## Overview

This dataset captures key macroeconomic indicators for Nepal spanning fiscal years 2077/78 to 2086/87 (AD 2021–2030). It is structured for economic analysis, forecasting, and dashboard development, and draws on official data from Nepal Rastra Bank (NRB) and the National Statistics Office (NSO).

---

## Repository Contents

| File | Type | Description |
|------|------|-------------|
| `nepal_economy_raw_data.csv` | Raw Data | Primary dataset with 10 annual records and 13 columns of macroeconomic indicators |
| `nepal_economy_data_dictionary.csv` | Reference | Column-level metadata: data types, descriptions, and source authorities |
| `nepal_economy_practice.xlsx` | Workbook | Working file with extended data (to 2030), derived metrics, KPI targets, pivot summaries, and a practice dashboard |

---

## Dataset Scope

- **Time period:** FY 2077/78 – FY 2086/87 (AD 2021 – 2030)
- **Granularity:** Annual (`Full_Year` aggregates)
- **Records:** 10 rows
- **Calendar systems:** Bikram Sambat (BS) and Anno Domini (AD) columns included side-by-side

---

## Column Reference

| Column | Type | Description | Source |
|--------|------|-------------|--------|
| `Row_ID` | Integer | Unique incremental row identifier | System Generated |
| `Fiscal_Year_BS` | String | Fiscal year in Bikram Sambat calendar (e.g., `2077/78`) | NRB |
| `Year_AD` | Integer | Corresponding AD calendar year | NRB |
| `Quarter` | String | Temporal slice — `Q1`, `Q2`, `Q3`, `Q4`, or `Full_Year` | NSO |
| `GDP_Real_Growth_Pct` | Float (%) | Annual real GDP growth rate, inflation-adjusted | NSO |
| `Agri_Sector_Growth_Pct` | Float (%) | Growth rate of the agricultural sector (crops, livestock, forestry, fisheries) | NSO |
| `Non_Agri_Sector_Growth_Pct` | Float (%) | Growth rate of manufacturing, construction, energy, and services | NSO |
| `CPI_Inflation_Avg_Pct` | Float (%) | Annual average Consumer Price Index inflation | NRB |
| `Remittance_Inflow_NPR_Billions` | Float | Total inbound remittances from migrant workers (Billions NPR) | NRB |
| `Total_Imports_NPR_Billions` | Float | Total import expenditure — CIF value (Billions NPR) | Customs / NRB |
| `Total_Exports_NPR_Billions` | Float | Total export revenue — FOB value (Billions NPR) | Customs / NRB |
| `FX_Reserves_USD_Billions` | Float | Gross foreign exchange reserves held by NRB (Billions USD) | NRB |
| `Import_Cover_Months` | Float | Number of months current FX reserves can cover imports | Derived / NRB |

---

## Derived Metrics (in XLSX workbook)

The practice workbook extends the raw data with the following computed fields:

- **`Total_Trade_NPR_Billions`** — Sum of total imports and exports
- **`Total_export_to_import_pct`** — Exports as a share of imports (export coverage ratio)

---

## KPI Targets (in XLSX workbook)

The workbook contains reference KPI targets for AD 2026:

| KPI | Target Value |
|-----|-------------|
| GDP Growth | 4.5% |
| Inflation | 4.5% |
| Remittance Inflow | NPR 1,750 Billion |
| FX Reserves | USD 23.5 Billion |

---

## XLSX Sheet Structure

| Sheet | Contents |
|-------|----------|
| `in` | Full dataset (2021–2030) with derived columns and 2026 KPI targets |
| `Sheet1` | Pivot table summaries — GDP, inflation, remittances, trade, and sector growth |
| `Practice_Dashboard` | Dashboard workspace for visualization practice |

---

## Data Sources

| Authority | Role |
|-----------|------|
| **Nepal Rastra Bank (NRB)** | Monetary indicators: CPI, remittances, FX reserves, imports/exports |
| **National Statistics Office (NSO)** | Growth indicators: GDP, agricultural sector, non-agricultural sector |
| **Department of Customs** | Trade flow data (jointly with NRB) |
| **System / Derived** | `Row_ID` and `Import_Cover_Months` computed from primary sources |

---

## Notes

- All monetary values denominated in **Nepalese Rupees (NPR)** unless stated as USD.
- Import and export values use standard international valuation conventions: **CIF** (Cost, Insurance, Freight) for imports; **FOB** (Free on Board) for exports.
- The dataset covers both historical actuals (2021–2025) and projected/estimated values (2026–2030).
- The Bikram Sambat fiscal year runs mid-July to mid-July; `Year_AD` reflects the ending calendar year of each BS fiscal year.
