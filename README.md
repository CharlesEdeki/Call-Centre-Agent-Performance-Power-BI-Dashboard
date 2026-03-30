# 🏥 Hospital Emergency Room Visits — Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Healthcare](https://img.shields.io/badge/Healthcare%20Analytics-605BFF?style=flat)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat)

> 📁 **[View Dashboard Files on Google Drive](https://drive.google.com/drive/folders/1v_tdyIn688WD9lpSigNOZlpR-qGxFhsj?usp=sharing)** — includes .pbix file and source dataset

---

## Overview

An interactive Power BI dashboard analysing **9,216 emergency room visits** across an 18-month period (April 2019 – October 2020). Tracks patient flow patterns, wait times, satisfaction scores, and departmental referrals — broken down by gender, age group, race, and time of day — to help ER administrators identify bottlenecks and improve care delivery.

> **Key Question:** *When are patients arriving, how long are they waiting, and which patient groups and departments are driving the most pressure on the ER?*

---

## Dashboard Preview

### 2020 Overview — All Visits
<img width="1066" height="594" alt="image" src="https://github.com/user-attachments/assets/c6f6ca43-c5c9-436d-bdb1-a06b0d86b8f7" />
> 505 visits in view · Avg wait time 36.18 mins · Avg satisfaction 4.90 · Busiest day: Wednesday at 11:00 AM

### 2019 Overview — Filtered View
<img width="1066" height="594" alt="image" src="https://github.com/user-attachments/assets/066b598f-94cc-488d-b533-6cd7fec2340c" />
> 154 visits in view · Avg wait time 35.27 mins · Busiest day: Saturday at 3:00 PM · Physiotherapy leads referral wait times at 44 mins

> 📁 **[Download full .pbix file and dataset → Google Drive](https://drive.google.com/drive/folders/1v_tdyIn688WD9lpSigNOZlpR-qGxFhsj?usp=sharing)**

---

## Dashboard Features

- **3 KPI Cards with Sparklines & MoM Change** — Patient visits, average wait time, and average satisfaction score, each showing month-over-month % change with trend sparklines
- **Patients by Weekday and Gender** — Dual-line chart comparing male and female visit patterns across the week, with gender split counters (256M / 249F in sample view)
- **Patients by Age Range** — Grouped bar chart segmenting visits into Adults, Children, and Seniors
- **24-Hour × 7-Day Heat Map** — The dashboard's centrepiece; a full matrix showing visit density by hour (00–23) and day of week, with dynamic busiest day and time callouts
- **Satisfaction Score by Race** — Ranked table with star ratings showing average satisfaction across 7 racial groups
- **Avg Wait Time by Department Referral** — Horizontal bar chart ranking departments from highest to lowest average wait time
- **Year and Month Slicers** — Left-panel filters for 2019/2020 and individual months, making the entire dashboard context-aware

---

## Key Insights

> **50% of patients were admitted**, suggesting the ER is handling a high proportion of serious cases — not just walk-in minor complaints. This has direct implications for bed availability and downstream ward pressure.

> **Monday is the busiest day overall** (1,377 visits), but the dashboard's dynamic DAX measure surfaces that the single busiest day shifts depending on the time period selected — Wednesday at 11:00 AM for 2020, Saturday at 3:00 PM for 2019. Static reports would miss this variation entirely.

> **Wait times are remarkably consistent across departments** — ranging from 34.7 mins (Renal) to 36.8 mins (Neurology) — suggesting the bottleneck is systemic (overall ER capacity) rather than department-specific. Targeted departmental fixes alone are unlikely to move the needle.

> **58.7% of visits had no satisfaction score recorded**, pointing to a data collection gap that limits the reliability of satisfaction analysis. Any satisfaction-based decisions should be treated with caution until capture rates improve.

> **Adults dominate ER visits** (5,489 vs 2,110 children and 1,617 seniors), but Children and Seniors represent higher-risk patient groups that may warrant dedicated triage pathways given their different care needs.

---

## Tools & Skills Demonstrated

| Area | Detail |
|---|---|
| Data Modelling | Custom Calendar table with DAX, linking date dimensions to patient records |
| DAX Measures | Dynamic busiest day/time using `TOPN` + `SUMMARIZE` + `MAXX` pattern |
| Time Intelligence | Month-over-month % change on all three KPI cards |
| Visualisation | Heat map matrix, dual-line chart, star rating table, KPI sparklines |
| Healthcare Context | ER patient flow, triage dynamics, admission rates, departmental referral analysis |

---

## How to Use

1. Download the `.pbix` file from the Google Drive link above
2. Open in **Power BI Desktop** (free from Microsoft)
3. Connect to `Hospital_ER.csv` when prompted
4. Use the **year (2019 / 2020)** and **month slicers** on the left panel to filter the entire dashboard
5. Toggle between **Age Range, Gender, and Race** tabs on the top-right panel for different demographic views
6. Hover over the heat map cells to see exact visit counts by hour and day

---

## Credits

Dashboard design inspired by a tutorial on the [Abdelytics](https://www.youtube.com/watch?v=Q8ftOjqfQSg&t=4679s). Data analysis and insights are my own work.

---

## About

Built by **Charles Edeki** — Data Analyst & Educator | Abuja, Nigeria
📧 charlesedeki093@gmail.com | [LinkedIn](https://www.linkedin.com/in/charles-edeki/) | [GitHub](https://github.com/CharlesEdeki)
