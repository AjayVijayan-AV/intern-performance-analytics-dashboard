# intern-performance-analytics-dashboard Analyzing intern performance data through KPI-driven insights, data preprocessing, and visualization to build an interactive analytics dashboard.

Analyzing intern performance data using KPI-driven insights, data preprocessing, and visualization to build an interactive analytics dashboard.

---

## 🛠️ Data Preprocessing & Engineering

The dataset underwent a structured preprocessing pipeline to ensure data quality, consistency, and readiness for analysis.

---

## Sprint 1: Data Collection & Preparation

Focused on cleaning and standardizing the raw **Intern Performance dataset (300 records)**.

### Data Cleaning & Missing Value Handling
- **late_submissions:** Filled missing values (61 records) with 0, assuming no record indicates no late submissions.
- **Work_accident:** Filled missing values (13 records) using mode (0) and removed invalid characters.

### Data Type Standardization
- **Dates:** Converted `start_date` and `end_date` into a consistent datetime format.
- **Numerical Fields:** Converted `attendance_rate` and `last_evaluation` from percentage strings (e.g., "95%") to numeric values.
- **Currency:** Standardized `stipend` as a numeric field for analysis.

### Data Validation
- Ensured logical consistency:
  - `tasks_completed ≤ tasks_assigned`
  - Applied constraint using:  
    `tasks_completed = MIN(tasks_completed, tasks_assigned)`

---

## 🚀 Intern Performance Analysis - Sprint 2

## 📝 Project Overview
Sprint 2 focused on transforming a raw dataset into a realistic, correlation-driven performance model. The goal was to move beyond random data points to establish meaningful relationships between intern behavior (learning, attendance, reliability) and their overall performance scores.

---

## 📊 Core KPI Definitions

We have finalized four primary Key Performance Indicators (KPIs) to monitor program success:

| KPI | Definition | Target |
| :--- | :--- | :--- |
| **Learning Engagement** | Average hours spent in professional development modules. | `> 30 Hours` |
| **Reliability Rate** | % of interns with 0 or 1 late submissions per month. | `> 80%` |
| **High Performer Ratio** | % of the cohort achieving a Performance Score > 7.5. | `> 25%` |
| **Efficiency Score** | Ratio of tasks completed vs. time spent (Scaled 1–10). | `> 7.0` |

---

## ⚙️ Technical Refinement Logic

The dataset was refined using weighted logic to ensure that high scores are "earned" through consistent professional behavior.

### 1. Performance Score Weighting

The `performance_score` is calculated using:

- **Attendance (25%)** – Base commitment  
- **Learning Hours (25%)** – Proactive growth  
- **Reliability (20%)** – Deduction based on `late_submissions`  
- **Completion (30%)** – `tasks_completed` vs. `tasks_assigned`  

---

### 2. Departmental Benchmarking

- **Data Science** → High-growth profile (Target: 40+ learning hours)  
- **Development** → Operational profile (Target: high efficiency/speed)  
- **HR** → Process-oriented profile (Target: high feedback/attendance)  

---

## 🧮 Necessary Formulas (Google Sheets / Excel)

### Data Cleaning (Stipend Fix)

```excel
=ARRAYFORMULA(AVERAGE(VALUE(SUBSTITUTE(SUBSTITUTE(Sheet1!L:L, "₹", ""), ",", ""))))
