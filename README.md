# Hospital Emergency Room Analytics Dashboard – Power BI

An end‑to‑end Power BI project analyzing Hospital Emergency Room (ER) performance, built from raw CSV data to an interactive multi‑page dashboard.

***

## Project Overview

This project focuses on monitoring and improving ER operations using data.  
The dashboard helps stakeholders track patient volume, waiting times, satisfaction scores, admission rates, and referrals across different time periods and patient segments.

**Key objectives:**

- Provide a quick view of core ER KPIs (patients, wait time, satisfaction, admissions, referrals).
- Identify patterns by time (year, month, day, hour) and demographics (age group, gender, race).
- Support data‑driven decisions around staffing, capacity planning, and service quality.

***

## Dataset

- Source: https://www.kaggle.com/datasets/xavierberge/hospital-emergency-dataset
- Size: ~9k rows, ~10–15 columns.
- Example fields:
  - Patient ID  
  - Admission date & time  
  - Gender, age, race  
  - Department / referral source  
  - Admission flag (Admitted / Not Admitted)  
  - Waiting time  
  - Satisfaction score

***

## Tech Stack & Skills

- Power BI Desktop
- Power Query (data cleaning & transformation)
- DAX (measures and calculated columns)

**Skills demonstrated:**

- Data cleaning and transformation in Power Query  
- Star‑schema style data modeling (Fact table + Date dimension)  
- DAX measures for KPIs and time intelligence  
- Interactive dashboard design and storytelling

***

## Data Modeling

- **Fact table:** ER visits (one row per patient visit).
- **Dimension table:** Date table created using a calendar function, with:
  - Date  
  - Year  
  - Month  
  - Month number  
  - Month‑Year

Relationships:

- Date[Date] → ER_Fact[AdmissionDate] (one‑to‑many).

Additional transformations:

- Standardized gender values (Male/Female/Not Confirmed).  
- Derived age groups (e.g., 0–9, 10–19, …, 100+).  
- Derived admission status text (Admitted / Not Admitted).

***

## Key DAX Measures

Some of the main measures created:

- **Total Patients** – distinct count of Patient ID.
- **Average Wait Time** – average of wait time in minutes.
- **Average Satisfaction Score** – average of satisfaction column.
- **Total Referrals** – count of patients with non‑null referral.

***

## Dashboard Pages

**Monthly View** : Monthly snapshot of KPIs with trends by day, including total patients, average wait time, satisfaction, referrals, and charts by age group, gender, race, admission status, and day/hour.
**Consolidated View** : Same KPIs over a custom date range using start/end date slicers, ideal for quarterly/annual analysis.
**Patient Details** : Tabular view of individual visits with search/slicer options for deeper record‑level analysis.
**Key Takeaways** : Narrative/insight page summarizing main findings such as busiest hours, dominant age groups, and wait‑time performance.

Common interactions:

- Slicers for year, month, date range, age group, gender, race, admission status, and referral source.  
- Cross‑filtering when clicking on charts (e.g., age group, race, day of week, hour).

***

## Insights (Examples)

You can customize this based on what you saw in your final report:

- Certain age groups (e.g., 30–50) contribute the highest ER visits.
- Some days and hours show clear peak load, indicating when more staff may be needed.
- A noticeable share of patients exceed the target 30‑minute waiting time.
- Admission vs non‑admission proportions highlight ER severity and bed‑capacity pressure.

***

## How to Use This Repo

1. Clone or download this repository.
2. Open the `.pbix` file in Power BI Desktop.  
3. If needed, update the data source path in **Transform Data** → **Data source settings**.
4. Refresh the data and interact with the report pages.  

***

## Project Structure

- `data/` – Raw or sample dataset.
- `pbix/` – Power BI report file.  
- `images/` – (https://github.com/253425aditya/Hospital-Emergency-Room-Dashboard/blob/main/Snapshot%20Of%20DashBoard.png).  
- `README.md` – Project documentation (this file).
