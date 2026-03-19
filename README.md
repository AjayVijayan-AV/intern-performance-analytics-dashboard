# intern-performance-analytics-dashboard
Analyzing intern performance data through KPI-driven insights, data preprocessing, and visualization to build an interactive analytics dashboard.
#🛠️ Data Preprocessing & Engineering

The dataset underwent a multi-stage preprocessing pipeline to ensure data integrity and to derive high-value features for performance analysis.
**Sprint 1:** **Data Collection & Preparation**

The focus was on cleaning the raw "Intern Performance" dataset (300 records) and standardizing data types.
**Missing Value Imputation:**
late_submissions: Missing entries (61 records) were filled with 0, under the domain assumption that no record indicates zero late submissions.
Work_accident: Missing entries (13 records) were imputed using the Mode (0). A data entry error (backtick characters) was also cleaned.
**Data Type Standardization:**
**Dates:** Converted start_date and end_date from varied text formats (e.g., mm/dd/yyyy) into standardized date objects (dd/mm/yyyy).
**Numerical Conversions: **Transformed attendance_rate and last_evaluation from percentage strings (e.g., "99%") to floating-point decimals for calculation.
**Currency:** Formatted stipend as a numeric currency field to facilitate financial aggregations.
Logical Validation:
**Task Cap Constraint:** Implemented a logical check to ensure tasks_completed never exceeds tasks_assigned.
**Formula:** tasks_completed = MIN(tasks_completed, tasks_assigned)

#Sprint 2: Feature Engineering & EDA Readiness

New metrics were engineered to provide a deeper understanding of intern efficiency and engagement beyond raw performance scores.
Key Feature Engineering:
**Completion Rate:** Measures the percentage of assigned work successfully finalized.
**Formula: **tasks_completed / tasks_assigned
**Internship Duration:** Calculates total tenure in days to identify the "learning curve" impact.
Formula: end_date - start_date
**Task Speed Index:** A comparative metric that benchmarks an individual intern's average task time against their specific department's mean.
**Formula:** individual_avg_task_time / departmental_mean_task_time
Exploratory Data Analysis (EDA) Support:
**Departmental Aggregation:** Generated summary statistics for Data Science, Dev, and HR to identify performance leaders and operational bottlenecks.
**Outlier Detection:** Prepared the dataset for histogram and box-plot analysis to identify top-tier (10.0 score) and low-performing interns.
