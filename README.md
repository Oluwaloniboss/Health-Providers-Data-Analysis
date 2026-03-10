# Healthcare Financial & Provider Performance Dashboard
## 📊 Project Overview
This repository contains a comprehensive Power BI dashboard developed to analyze the financial performance and provider efficiency of a healthcare center. The project transforms raw healthcare data into actionable insights for stakeholders, focusing on revenue streams, departmental performance, and patient costs.
The analysis follows a structured approach based on a provided requirements document, covering KPI tracking, trend analysis, and detailed provider insights.
## 🎯 Objective
- Analyze Financial Performance: Identify key revenue drivers (procedures, departments), track billing amounts, and understand cost structures (medication, treatment, room charges).
- Evaluate Provider Performance: Assess the efficiency and billing patterns of different medical departments (Cardiology, Orthopedics, etc.).
- Identify Trends: Uncover patterns over time and across different service types (Emergency, Inpatient, Outpatient).
- Deliver an Interactive Dashboard: Create a user-friendly, 4-page dashboard for stakeholders to explore the data themselves.
## 🛠️ Tools & Technologies
- Data Visualization: Microsoft Power BI
- Data Modeling: DAX (Data Analysis Expressions)
- Data Source: Provided Healthcare Dataset (CSV/Excel)
- Design: Microsoft PowerPoint (for custom dashboard backgrounds)

## 🔑 Key Features & Measures
### Data Modeling
- Star Schema: Designed a relational model connecting fact tables to dimension tables (e.g., Date, Procedure, Department).
- DAX Measures Table: Created a dedicated table to store all calculated measures for better organization and performance.
### Core DAX Measures
- `Total Billing = SUM('Healthcare'[Billing Amount])`
- `Avg Billing per Patient = AVERAGE('Healthcare'[Billing Amount])`

- `Total Medication Cost`, `Total Treatment Cost`, `Total Insurance`, `Total Out of Pocket`
- `% of Grand Total = DIVIDE([Total Billing], CALCULATE([Total Billing], ALL('DimensionTable')))`
- Dynamic Date Table: Generated using `CALENDARAUTO()` with columns for Year, Quarter, Month, and Week, including proper sort columns (`MonthNum`, `WeekNum`).

### Dashboard KPIs
1.  Financial Overview:
    - High-level KPI cards with embedded averages (reference labels).
    - Revenue breakdown by procedure with percentage of grand total.
    - Stacked bar chart: Billing by Diagnosis colored by Service Type (Emergency/Inpatient/Outpatient).

2.  Provider Insights:
    - Department performance (Total Billing vs. % of Grand Total).
    - Analysis of Out-of-Pocket costs by department to assess patient financial burden.
    - Detailed department metrics table.

3.  Trend Analysis:
    - Time-series line charts of revenue (drill-down from Year to Month).
    - Tracking the popularity of procedures and diagnoses over time.

4.  Additional Insights:
    - Azure Map: Geographic distribution of billing by State and City.
    - Parameter Slicer: Dynamic control for the map to filter by Year/Quarter.
    - Payer mix analysis (Insurance vs. Out of Pocket).

## 🚀 How to Use
 Download the `.pbix` file

## 💡 Insights & Recommendations
- Top Revenue Generators: X-Ray (31%) and CT Scan (24%) are the most billed procedures. Ensuring their operational efficiency is key.
- Department Focus: Cardiology and Orthopedics lead in billing but also contribute the most to patient out-of-pocket costs. A billing audit could reveal savings opportunities.
- Service Type Patterns: Asthma and Migraine show high outpatient activity, suggesting potential for expanded ambulatory care services.
- Geographic Targeting: The map view can guide resource allocation and marketing efforts to high-potential states/cities.

## 📝 Future Work
- Integrate patient satisfaction scores to correlate with financial performance.
- Build predictive models to forecast future billing amounts based on historical trends.
- Perform a deeper analysis on payer mix to negotiate better insurance contracts.

