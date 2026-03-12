# Covid-healthcare-powerbi-dashboard
Interactive 3-page Power BI dashboard analyzing global COVID-19 data with Azure Maps, heatmap matrix, RLS security roles and DAX measures.
# 🦠 COVID-19 Global Analytics Dashboard — Power BI

## Overview
An intermediate-to-advanced Power BI dashboard analyzing 
global COVID-19 spread across 180+ countries from 
January to July 2020. Built to demonstrate enterprise-grade 
BI skills including Row Level Security, Azure Maps, 
DAX measures, and interactive drillthrough navigation.

## 📊 Dashboard Pages

### Page 1 — Global Overview
- 4 KPI cards: Total Confirmed, Total Deaths, 
  Total Recovered, Death Rate %
- Azure Bubble Map: Case distribution across 
  180+ countries with bubble size = confirmed cases
- Line chart: Monthly confirmed cases and 
  deaths trend (Jan–Jul 2020)
- Continent slicer for regional filtering

### Page 2 — Country Comparison
- Top 10 countries bar chart sorted by 
  confirmed cases
- Heatmap Matrix: Country × Month with 
  gradient conditional formatting 
  (darker = more cases)
- Scatter plot: Confirmed vs Deaths with 
  ratio line identifying countries with 
  disproportionately high death rates
  - What-If Death Rate Simulator: dynamic 
  slider adjusting from 0% to 20% to model 
  worst case scenarios in real time
- Side by side Actual vs Adjusted Death 
  Rate % cards showing instant impact 
  of scenario changes
  

### Page 3 — Country Drillthrough
- Drillthrough from any country data point
- Per-country KPIs: Confirmed, Deaths, 
  Recovery Rate %
- Monthly trend line chart
- Month-by-month breakdown table 
  with Death Rate %
- Back button navigation

## 🔐 Row Level Security (RLS)
Continent-based security roles restricting 
data access per analyst:

| Role | Access |
|------|--------|
| African Analyst | Africa only |
| Asian Analyst | Asia only |
| European Analyst | Europe only |

When a role is applied the entire dashboard — 
KPIs, map, charts and slicers — automatically 
filters to show only that continent's data.

## 📊 What-If Analysis (Scenario Modelling)
Built a dynamic Death Rate Scenario Simulator 
using Power BI What-If parameters:

- Adjustable slider from 0% to 20% increment 0.01
- Actual Death Rate % card — current real value
- Adjusted Death Rate % card — simulated value
- Allows healthcare planners to model worst 
  case death rate scenarios in real time

Example: Setting adjustment to 13% increases 
simulated death rate from 5.24% to 18.24% 
instantly across the dashboard.

## 🔧 Technical Features
- Star schema data model with 3 tables:
  COVID (fact), Countries (dimension), 
  Date (dimension)
- Dedicated DAX Date table with time intelligence
- Power Query ETL: data type enforcement, 
  merge queries, continent lookup
- Bidirectional cross-filtering for RLS propagation
- Azure Maps visual (upgraded from deprecated map)
- Gradient conditional formatting on matrix

## 📐 DAX Measures
| Measure | Description |
|---------|-------------|
| Total Confirmed | SUM of confirmed cases |
| Total Deaths | SUM of deaths |
| Total Recovered | SUM of recovered cases |
| Total Active | Active cases count |
| Death Rate % | Deaths / Confirmed |
| Recovery Rate % | Recovered / Confirmed |
| Active Cases | Confirmed - Deaths - Recovered |
| Case Fatality Rate % | Deaths / Closed cases |

## 📁 Files
| File | Description |
|------|-------------|
| COVID_Healthcare_Dashboard.pbix | Power BI report |
| covid_19_clean_complete.csv | Daily country data |
| worldometer_data.csv | Country summary stats |

## 📷 Screenshots
![Global Overview](page1_global.png)
![Country Comparison](page2_comparison.png)
![Country Drillthrough](page3_drillthrough.png)
![RLS Africa View](rls_africa.png)

## 🗂️ Dataset
https://www.kaggle.com/datasets/imdevskp/corona-virus-report
- 180+ countries
- Daily data January–July 2020
- Columns: Date, Country, Confirmed, 
  Deaths, Recovered, Active, WHO Region

## 🛠️ Tools Used
- Power BI Desktop
- Power Query (ETL & merge queries)
- DAX (calculated measures)
- Azure Maps visual
- Row Level Security (RLS)
```

---

