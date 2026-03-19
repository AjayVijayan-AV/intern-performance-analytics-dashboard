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

## Sprint 2: Feature Engineering & EDA Readiness

Created new metrics to enhance performance analysis and prepare the dataset for exploratory analysis.

### Feature Engineering
- **Completion Rate:**  
  `tasks_completed / tasks_assigned`
- **Internship Duration:**  
  `end_date - start_date`
- **Task Speed Index:**  
  `individual_avg_task_time / departmental_mean_task_time`

### EDA Preparation
- **Department-wise Aggregation:** Generated summary statistics across departments (Data Science, Development, HR).
- **Outlier Detection Ready:** Prepared data for histogram and boxplot analysis to identify high and low performers.

---
