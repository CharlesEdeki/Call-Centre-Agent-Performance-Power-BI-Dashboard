# 🏥 Hospital Emergency Room Visits — Power BI Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![Healthcare](https://img.shields.io/badge/Healthcare%20Analytics-605BFF?style=flat)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat)

> 📁 **[View Dashboard Files on Google Drive](https://drive.google.com/drive/folders/1v_tdyIn688WD9lpSigNOZlpR-qGxFhsj?usp=sharing)** — includes .pbix file and source dataset

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

## Problem Statement

Emergency rooms operate under relentless pressure — every minute of unnecessary waiting carries both human and financial cost. This analysis examines **9,216 ER visits** across 18 months (April 2019 – October 2020) to identify when patient demand peaks, where the system strains, and which structural patterns drive poor outcomes.

With an average wait time of **35.26 minutes** and a **50% admission rate**, this is not a minor care facility handling walk-in complaints. Half the patients coming through are being admitted — meaning the ER is continuously feeding a downstream ward system that must absorb whatever the ER sends it.

> **Key Question:** *When does the ER come under the most pressure, which patient groups are most affected, and where does the data point toward actionable operational change?*

---

## Dataset

| Field | Detail |
|---|---|
| Source | Simulated ER patient records |
| Total records | 9,216 visits |
| Period | April 2019 – October 2020 (18 months) |
| Variables | Date/time, age, gender, race, wait time, satisfaction score, admission flag, department referral |

---

## Dashboard Features

- **3 KPI Cards with Sparklines & MoM Change** — Patient visits, average wait time, and average satisfaction score with month-over-month % change indicators
- **Patients by Weekday and Gender** — Dual-line chart comparing male and female visit patterns across the week
- **Patients by Age Range** — Grouped bar chart across Adults, Children, and Seniors
- **24-Hour × 7-Day Heat Map** — Full visit density matrix by hour and day, with dynamic DAX-powered busiest day and time callouts
- **Satisfaction Score by Race** — Ranked table with star ratings across 7 demographic groups
- **Avg Wait Time by Department Referral** — Horizontal bar chart from highest to lowest wait per department
- **Year and Month Slicers** — Left-panel filters making the entire dashboard context-aware

---

## Current Condition

### Headline Metrics

| Metric | Value |
|---|---|
| Total Visits | 9,216 |
| Period | Apr 2019 – Oct 2020 |
| Avg Wait Time | **35.26 mins** |
| Avg Satisfaction Score | **4.99 / 10** |
| Admission Rate | **50.0%** |
| Missing Satisfaction Records | **72.7%** (6,699 of 9,216) |

### Patient Volume Patterns

**Monday is the single busiest day** with 1,377 visits — 9% more than Friday (1,260), the quietest day. However, the dashboard's dynamic DAX measure reveals that the busiest day shifts across time periods: Wednesday at 11:00 AM dominates in 2020, while Saturday at 3:00 PM leads in 2019. A static weekly rota misses this temporal variation entirely.

The five **peak arrival hours by volume** are:

| Hour | Visits |
|---|---|
| 11 PM (23:00) | 436 |
| 7 AM | 415 |
| 1 PM | 410 |
| 12 AM (00:00) | 406 |
| 11 AM | 403 |

Late-night and early-morning surges are as significant as afternoon peaks — the ER does not have a predictable "quiet period" that could reliably absorb staffing reductions.

### Wait Times: Systemic, Not Departmental

Average wait times across all department referrals are strikingly uniform:

| Department | Avg Wait (mins) | Avg Satisfaction |
|---|---|---|
| Neurology | 36.80 | 5.28 |
| Physiotherapy | 36.57 | 4.99 |
| Gastroenterology | 35.83 | **5.80** |
| Cardiology | 35.35 | 5.14 |
| Orthopedics | 34.98 | 4.86 |
| General Practice | 34.91 | 5.06 |
| Renal | 34.70 | **4.57** |

The 2.1-minute spread between the highest (Neurology, 36.8) and lowest (Renal, 34.7) wait departments is negligible. This rules out any single department as the bottleneck — the constraint is **overall ER capacity**, not a specific clinical pathway. Targeted departmental fixes will not materially improve performance.

### Age Group Analysis

Adults make up the majority of visits (5,489) but Children show the highest admission rate:

| Age Group | Visits | Admission Rate | Avg Wait |
|---|---|---|---|
| Children | 2,110 | **51.3%** | 35.32 mins |
| Adults | 5,489 | 49.7% | 35.25 mins |
| Seniors | 1,617 | 49.7% | 35.21 mins |

Children arriving at the ER are marginally more likely to be admitted than adults — a finding that argues for dedicated paediatric triage pathways to avoid mixing high-risk child cases with the general adult flow.

### Satisfaction Data Gap

**72.7% of visits have no satisfaction score recorded** (6,699 of 9,216). The 2,517 scores that do exist show an average of 4.99/10 — a middling result. But any operational decision based on satisfaction data is working from less than 30% of the actual patient experience. The data collection process is the first thing that needs fixing before satisfaction metrics can meaningfully inform management.

---

## Root Cause Analysis

1. **Capacity constraint is universal, not localised** — the consistency of wait times across departments indicates the bottleneck is total throughput capacity, not any individual clinical area
2. **Demand is unpredictable across the full 24-hour window** — late-night and early-morning surges match daytime peaks, making traditional shift patterns a poor fit for actual demand
3. **50% admission rate creates continuous downstream pressure** — half of all ER patients are transitioning to wards, creating a chronic bed management problem that the ER alone cannot solve
4. **Satisfaction data is too sparse to act on** — the 72.7% missing score rate means the patient experience is essentially unmeasured at current collection rates

---

## Desired Condition

- Staffing levels that respond to the actual 24-hour demand distribution rather than fixed shift patterns
- Avg wait time reduced below 25 minutes through capacity planning aligned to peak windows
- Satisfaction score capture rate above 80% to enable data-driven patient experience improvements
- Dedicated paediatric triage stream to manage the higher admission rate for children
- Real-time occupancy visibility for downstream wards to smooth the admission handoff

---

## Recommendations

**1. Demand-aligned staffing model**
Replace fixed shift patterns with a demand-responsive rota built from the heat map data. The 23:00, 07:00, and 13:00 peak hours — plus Monday as the consistently highest-volume day — should anchor staffing decisions, not generic shift templates.

**2. Address the bed pipeline, not just the ER**
With 50% of patients being admitted, ER wait time improvement is fundamentally linked to ward bed availability. Reducing ER dwell time requires a coordinated discharge acceleration programme upstream, not just ER-side changes.

**3. Fix satisfaction data collection immediately**
A 72.7% missing rate renders the satisfaction metric almost meaningless. Deploying a simple post-visit SMS or kiosk survey at discharge would rapidly improve data density and enable genuine patient experience monitoring.

**4. Paediatric fast-track pathway**
Children's higher admission rate and distinct care needs justify a dedicated paediatric assessment stream during peak hours, reducing the risk of high-acuity child cases waiting alongside adult general presentations.

---

## Tools & Skills Demonstrated

| Area | Detail |
|---|---|
| Data Analysis | Python (Pandas) — 9,216 records, age segmentation, hourly demand profiling |
| DAX Measures | Dynamic busiest day/time using `TOPN` + `SUMMARIZE` + `MAXX` |
| Time Intelligence | Month-over-month % change, custom Calendar table |
| Visualisation | Heat map matrix, dual-line chart, star rating table, KPI sparklines |
| Healthcare Context | ER patient flow, triage dynamics, admission-discharge management |

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
