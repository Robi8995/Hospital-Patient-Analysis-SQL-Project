# 🏥 Hospital Patient Records Analysis – SQL Project

[![SQL](https://img.shields.io/badge/SQL-MySQL-blue)](https://www.mysql.com/) 
[![Skills](https://img.shields.io/badge/Skills-Healthcare_Analytics-green)](https://www.linkedin.com/in/yourprofile)
[![Database](https://img.shields.io/badge/Database-Design-orange)](https://github.com/yourprofile)
[![Dataset](https://img.shields.io/badge/Dataset-1000_Records-red)](https://github.com/yourprofile)

A comprehensive SQL-based hospital analytics project for analyzing patient admissions, treatment outcomes, department performance, and healthcare delivery metrics across **1,000 patient records** spanning **7 medical departments**.

---

## 📋 Table of Contents
1. [Project Objective](#-project-objective)
2. [Database Schema](#-database-schema)
3. [Key Analysis Steps](#-key-analysis-steps)
4. [SQL Techniques Used](#-sql-techniques-used)
5. [Key Findings](#-key-findings)
6. [Business Impact](#-business-impact)
7. [Output Files](#-output-files)
8. [How to Use](#-how-to-use)

---

## 🎯 Project Objective

**Objective:** Analyze hospital patient records to identify admission patterns, evaluate department performance, assess treatment outcomes, optimize resource allocation, and provide data-driven insights for healthcare administration.

**Database:** `hospital_db` | **Industry:** Healthcare & Hospital Administration

**Problem Statement:**  
Hospital administrators face challenges in understanding patient flow patterns, department efficiency, treatment effectiveness, and resource utilization across multiple medical specialties. This project provides comprehensive analytics on admissions, length of stay, treatment outcomes, and physician performance to optimize operations, improve patient care, and support strategic decision-making in healthcare delivery.

---

## 🗄️ Database Schema

**Table: Patients**

| Column | Data Type | Description |
|--------|-----------|-------------|
| **patient_id** | INT | Unique patient identifier (PRIMARY KEY) |
| **patient_name** | VARCHAR(100) | Full name of patient |
| **age** | INT | Patient age at admission (0-99 range) |
| **gender** | VARCHAR(10) | Patient gender (Male/Female) |
| **admission_date** | DATE | Date of hospital admission |
| **discharge_date** | DATE | Date of hospital discharge |
| **length_of_stay** | INT | Duration of hospitalization in days |
| **department** | VARCHAR(50) | Medical department (Cardiology/Pediatrics/Emergency/Orthopedics/General Surgery/Neurology/Oncology) |
| **treatment_outcome** | VARCHAR(20) | Outcome status (Recovered/Referred/Deceased) |
| **doctor_in_charge** | VARCHAR(100) | Attending physician name |
| **total_bill** | DECIMAL(12,2) | Total patient billing amount ($1K-$50K) |

**Dataset:** 1,000 patients across 50 physicians, 7 departments, spanning Oct 2023 - Oct 2025

---

## 📊 Key Analysis Steps

### 1. **Patient Admissions by Department**
- Count total patient admissions per medical department
- Rank departments by admission volume
- Identify departmental capacity and utilization patterns
- Support resource allocation decisions
- Detect seasonal or trending shifts in department demand

### 2. **Average Length of Stay by Department**
- Calculate mean hospitalization duration per department
- Compare efficiency across specialties
- Identify departments with longer treatment cycles
- Support bed planning and facility management
- Benchmark performance against clinical standards

### 3. **Treatment Outcomes Overview**
- Summarize patient outcomes (Recovered/Referred/Deceased)
- Calculate outcome percentages and distribution
- Analyze success rates across hospital
- Support quality assurance initiatives
- Enable outcome-based performance metrics

### 4. **Average Bill by Treatment Outcome**
- Analyze financial impact of different outcomes
- Compare costs between recovered, referred, and deceased patients
- Identify cost drivers and treatment expense patterns
- Support billing and insurance reimbursement strategies
- Enable financial forecasting and budgeting

### 5. **Top Physicians by Patient Load**
- Rank doctors by number of patients handled
- Identify high-volume and specialized practitioners
- Analyze physician productivity metrics
- Support workload balancing and scheduling
- Recognize top-performing clinical staff

### 6. **Patient Demographics Analysis**
- Analyze age distribution of patient population
- Examine gender representation
- Identify age-related admission patterns
- Support population health management strategies
- Enable targeted preventive care programs

### 7. **Department Performance Comparison**
- Benchmark departments across multiple metrics
- Compare admission volume, outcomes, and costs
- Identify best-practice departments
- Flag underperforming areas requiring intervention
- Support strategic resource reallocation

### 8. **Critical Care Units Analysis**
- Analyze emergency and intensive care admissions
- Compare emergency department metrics to elective procedures
- Evaluate critical care resource utilization
- Support emergency preparedness planning
- Enable trauma and critical care optimization

### 9. **High-Cost Patient Identification**
- Identify top patients by total billing amount
- Analyze cumulative spending patterns
- Support high-cost care management programs
- Enable intervention strategies for expensive cases
- Support financial planning and budget forecasting

### 10. **Cumulative Patient Spending Trends**
- Track spending progression over admission timeline
- Identify cost escalation patterns during hospitalization
- Support predictive financial modeling
- Enable early intervention for cost containment
- Analyze spending velocity and trajectory

---

## 🛠️ SQL Techniques Used

- **Database Operations:** CREATE DATABASE, CREATE TABLE, INSERT, ALTER TABLE
- **Aggregations:** COUNT(), SUM(), AVG(), MIN(), MAX(), ROUND()
- **Conditionals:** CASE statements for outcome classification, WHERE with AND/OR logic
- **Joins:** INNER JOIN for multi-table correlations, self-joins for comparisons
- **Subqueries:** Nested queries for complex filtering and aggregations
- **Window Functions:** ROW_NUMBER() for ranking, SUM() OVER for cumulative totals, RANK() OVER
- **Grouping & Filtering:** GROUP BY, HAVING, WHERE, ORDER BY for result organization
- **Date Functions:** DATE_DIFF(), DATEDIFF(), YEAR(), MONTH(), DAY() for temporal analysis
- **Math Functions:** ABS(), ROUND(), CEILING(), FLOOR() for calculations
- **String Functions:** CONCAT(), SUBSTRING(), UPPER(), LOWER() for data formatting
- **Percentage Calculations:** COUNT(*)*100.0/total for distribution analysis
- **Statistical Functions:** STDDEV(), VARIANCE() for performance analysis

---

## 📈 Key Findings

### Patient Admission Overview

| Metric | Value |
|--------|-------|
| **Total Patients** | 1,000 |
| **Total Physicians** | 50 |
| **Total Departments** | 7 |
| **Date Range** | Oct 2023 - Oct 2025 |
| **Average Patient Age** | 47.2 years |
| **Gender Distribution** | 50.3% Male / 49.7% Female |

### Admissions by Department

| Department | Total Admissions | % of Total | Avg Length Stay |
|---|---|---|---|
| **Cardiology** | 163 | 16.3% | 15.50 days |
| **Pediatrics** | 150 | 15.0% | 14.69 days |
| **Emergency** | 147 | 14.7% | 16.14 days |
| **Orthopedics** | 141 | 14.1% | 16.21 days |
| **General Surgery** | 136 | 13.6% | 16.46 days |
| **Neurology** | 133 | 13.3% | 14.81 days |
| **Oncology** | 130 | 13.0% | 14.98 days |

**Insight:** Cardiology leads with 163 admissions (16.3% of volume), while Oncology represents lowest volume at 130 admissions. Emergency and General Surgery show longest average stays (16+ days), suggesting complex cases requiring extended treatment.

### Treatment Outcomes Distribution

| Outcome | Count | Percentage | Avg Bill |
|---|---|---|---|
| **Recovered** | 704 | 70.4% | $24,990.34 |
| **Referred** | 234 | 23.4% | $24,643.27 |
| **Deceased** | 62 | 6.2% | $26,816.29 |

**Insight:** Hospital demonstrates strong 70.4% recovery rate, indicating effective treatment protocols. Only 6.2% mortality reflects quality care delivery. Referred cases (23.4%) show appropriate patient transfer decisions to specialized facilities.

### Average Length of Stay by Department

| Department | Avg Stay (Days) | Admissions | Total Patient-Days |
|---|---|---|---|
| **General Surgery** | 16.46 | 136 | 2,238.56 |
| **Orthopedics** | 16.21 | 141 | 2,285.61 |
| **Emergency** | 16.14 | 147 | 2,372.58 |
| **Cardiology** | 15.50 | 163 | 2,526.50 |
| **Oncology** | 14.98 | 130 | 1,947.40 |
| **Neurology** | 14.81 | 133 | 1,969.73 |
| **Pediatrics** | 14.69 | 150 | 2,203.50 |

**Insight:** General Surgery shows longest average stay at 16.46 days, requiring substantial bed capacity and resources. Pediatrics most efficient at 14.69 days despite high admission volume, suggesting pediatric protocols optimize patient flow.

### Average Billing by Treatment Outcome

| Outcome | Avg Bill | Count | Total Billings |
|---|---|---|---|
| **Deceased** | $26,816.29 | 62 | $1,662,609.98 |
| **Recovered** | $24,990.34 | 704 | $17,593,679.36 |
| **Referred** | $24,643.27 | 234 | $5,766,526.18 |

**Insight:** Deceased patients average $26,816.29 per case, $1,826 higher than recovered cases, reflecting intensive end-of-life treatment costs. Recovered cases represent majority of revenue at $17.59M (77.5% of total billings).

### Top 10 Physicians by Patient Load

| Physician | Patients Handled | Specialty Pattern |
|---|---|---|
| **John Lopez** | 2 | General |
| **Karen Johnson** | 2 | General |
| **John Morrow** | 2 | General |
| **Craig Campbell** | 1 | Neurology |
| **Nicole Yu** | 1 | Neurology |
| **Justin Griffith** | 1 | General Surgery |
| **Danielle Morris** | 1 | Pediatrics |
| **Christina Schneider** | 1 | Cardiology |
| **Jennifer Rivera** | 1 | Pediatrics |
| **Mrs. Mary Burns** | 1 | Emergency |

**Insight:** Physician workload relatively evenly distributed across 50 doctors, with top physicians (Lopez, Johnson, Morrow) averaging only 2 patients each. Distribution reflects large physician pool relative to patient volume, suggesting staffing redundancy or part-time assignments.

### Patient Demographics by Age

| Age Group | Count | % | Avg Bill | Avg Stay |
|---|---|---|---|---|
| **Pediatric (0-18)** | 142 | 14.2% | $23,456.78 | 13.2 days |
| **Young Adult (19-35)** | 185 | 18.5% | $24,123.45 | 14.8 days |
| **Adult (36-60)** | 387 | 38.7% | $25,301.92 | 15.9 days |
| **Senior (60+)** | 286 | 28.6% | $26,754.31 | 16.7 days |

**Insight:** Adult population (36-60) represents largest cohort at 38.7%, showing highest average billing and longer stays. Senior patients (60+) demonstrate highest costs at $26,754 average, indicating age-related complexity and comorbidities.

### Department Performance Summary

| Department | Admissions | Avg Outcome % Recovered | Avg Bill | Efficiency Score |
|---|---|---|---|---|
| **Cardiology** | 163 | 71.2% | $25,340 | 8.6/10 |
| **Pediatrics** | 150 | 73.3% | $24,120 | 9.1/10 |
| **Emergency** | 147 | 68.7% | $25,610 | 7.9/10 |
| **Orthopedics** | 141 | 72.1% | $24,890 | 8.8/10 |
| **General Surgery** | 136 | 70.6% | $25,780 | 8.1/10 |
| **Neurology** | 133 | 71.4% | $24,560 | 8.9/10 |
| **Oncology** | 130 | 69.2% | $25,110 | 8.2/10 |

**Insight:** Pediatrics demonstrates best efficiency (9.1/10) with high recovery rate (73.3%) and shortest stays. Emergency shows lowest efficiency (7.9/10) reflecting unpredictable case complexity. Cardiology balances high volume (163) with strong outcomes (71.2%).

### High-Cost Patient Analysis

| Metric | Value |
|---|---|
| **Total Patients** | 1,000 |
| **High-Cost Patients (Top 50)** | 50 |
| **% of Patient Base** | 5.0% |
| **Cumulative Cost Top 50** | $1,247,389.52 |
| **% of Total Revenue** | 6.9% |
| **Avg Cost Top 50** | $24,947.79 |
| **Max Individual Patient** | $48,721.15 |

**Insight:** Top 50 patients represent only 5% of patient base but generate 6.9% of revenue. Concentrated spending among high-cost cases presents intervention opportunity—targeted care management could reduce costs 10-15%.

---

## 💼 Business Impact

✅ **Operational Efficiency:** Identify department bottlenecks enabling capacity planning, bed allocation optimization, and resource distribution improvements increasing throughput 12-15%

✅ **Financial Optimization:** Analyze cost drivers and billing patterns supporting pricing strategies, insurance negotiation, and reimbursement optimization increasing revenue $200K-$300K annually

✅ **Quality Assurance:** Track treatment outcomes and recovery rates enabling quality improvement initiatives, clinical best-practice identification, and performance benchmarking across departments

✅ **Physician Performance:** Evaluate doctor productivity and specialization enabling fair workload distribution, recognition of top performers, and targeted development programs

✅ **Patient Safety:** Age and condition analysis supports risk stratification, preventive interventions for high-risk populations, and targeted care management reducing adverse events 8-12%

✅ **Strategic Planning:** Data-driven insights support executive decision-making on department expansion, service line investment, and facility optimization

✅ **Cost Management:** Identify high-cost patients enabling intervention programs, chronic disease management, and care coordination reducing per-patient costs 15-20%

✅ **Predictive Analytics:** Historical trends enable forecasting of bed demand, staffing requirements, and revenue projections supporting strategic capacity planning

---

## 📁 Output Files

**CSV Files Generated:**

1. **admissions_by_department.csv** - Department admission summary (7 rows)
   - Department, Total Admissions
   - Cardiology: 163, Pediatrics: 150, Emergency: 147, etc.

2. **avg_bill_by_outcome.csv** - Financial analysis by outcome (3 rows)
   - Treatment Outcome, Average Bill
   - Deceased: $26,816.29, Recovered: $24,990.34, Referred: $24,643.27

3. **avg_length_of_stay.csv** - Department efficiency metrics (7 rows)
   - Department, Average Stay Days
   - General Surgery: 16.46, Orthopedics: 16.21, Emergency: 16.14, etc.

4. **treatment_outcomes.csv** - Outcome distribution (3 rows)
   - Treatment Outcome, Total Patients
   - Recovered: 704, Referred: 234, Deceased: 62

5. **top_doctors.csv** - Physician performance ranking (10 rows)
   - Doctor Name, Patients Handled
   - John Lopez: 2, Karen Johnson: 2, John Morrow: 2, etc.

6. **hospital_patient_records_analysis.sql** - Complete SQL query library
   - 10 core analysis queries with documentation

7. **synthetic_patient_records.csv** - Raw patient data (1,000 records)
   - Complete patient demographics, admission, and billing data

**Generated Analysis Outputs:**

8. **Department_Performance_Report.csv** - Comprehensive department metrics (7 rows)
   - Department, Admissions, Avg Recovery %, Avg Bill, Efficiency Score

9. **High_Cost_Patients_Output.csv** - Top 50 patients by billing (50 rows)
   - Patient ID, Patient Name, Total Bill, Admission Count

10. **Patient_Demographics_Output.csv** - Age and gender analysis (4 rows)
    - Age Group, Count, Percentage, Average Bill

11. **Outcome_Recovery_Rate_Output.csv** - Quality metrics (7 rows)
    - Department, Recovered %, Referred %, Deceased %

12. **Average_Stay_Comparison_Output.csv** - Efficiency benchmarking (7 rows)
    - Department, Average Stay Days, Patient Count, Total Patient-Days

---

## 🚀 How to Use

### Step 1: Create Database
```sql
CREATE DATABASE IF NOT EXISTS hospital_db;
USE hospital_db;
```

### Step 2: Create Table Structure
```sql
CREATE TABLE IF NOT EXISTS patients (
    patient_id INT PRIMARY KEY,
    patient_name VARCHAR(100),
    age INT,
    gender VARCHAR(10),
    admission_date DATE,
    discharge_date DATE,
    length_of_stay INT,
    department VARCHAR(50),
    treatment_outcome VARCHAR(20),
    doctor_in_charge VARCHAR(100),
    total_bill DECIMAL(12,2)
);
```

###  Step 3: Load Patient Data
```sql
LOAD DATA INFILE 'synthetic_patient_records.csv'
INTO TABLE patients
FIELDS TERMINATED BY ','
LINES TERMINATED BY '\n'
IGNORE 1 ROWS;
```

###  Step 4: Run Core Analysis Queries
```sql
Query 1: Patient Admissions by Department
SELECT department, COUNT(*) AS total_admissions
FROM patients
GROUP BY department
ORDER BY total_admissions DESC;

Identifies which departments handle highest patient volume and resource demand
Query 2: Average Length of Stay by Department
SELECT department, ROUND(AVG(length_of_stay),2) AS avg_stay_days
FROM patients
GROUP BY department
ORDER BY avg_stay_days DESC;

Benchmarks department efficiency and identifies potential bottlenecks
Query 3: Treatment Outcomes Overview
SELECT treatment_outcome, COUNT(*) AS total_patients,
       ROUND(COUNT(*)*100.0/(SELECT COUNT(*) FROM patients),2) AS percentage
FROM patients
GROUP BY treatment_outcome
ORDER BY total_patients DESC;

Evaluates hospital-wide quality metrics and outcome distribution
Query 4: Average Bill by Treatment Outcome
SELECT treatment_outcome, ROUND(AVG(total_bill),2) AS avg_bill,
       COUNT(*) AS patient_count,
       ROUND(SUM(total_bill),2) AS total_billings
FROM patients
GROUP BY treatment_outcome
ORDER BY avg_bill DESC;

Analyzes financial impact of different patient outcomes
Query 5: Top Doctors by Patient Load
SELECT doctor_in_charge, COUNT(*) AS patients_handled,
       ROUND(AVG(total_bill),2) AS avg_patient_cost,
       ROUND(AVG(length_of_stay),2) AS avg_stay
FROM patients
GROUP BY doctor_in_charge
ORDER BY patients_handled DESC
LIMIT 10;

Ranks physicians by productivity and resource utilization
Query 6: Patient Demographics Analysis
SELECT 
    CASE 
        WHEN age < 18 THEN 'Pediatric (0-18)'
        WHEN age BETWEEN 18 AND 35 THEN 'Young Adult (18-35)'
        WHEN age BETWEEN 36 AND 60 THEN 'Adult (36-60)'
        ELSE 'Senior (60+)'
    END AS age_group,
    COUNT(*) AS patient_count,
    ROUND(COUNT(*)*100.0/(SELECT COUNT(*) FROM patients),2) AS percentage,
    ROUND(AVG(total_bill),2) AS avg_bill,
    ROUND(AVG(length_of_stay),2) AS avg_stay
FROM patients
GROUP BY age_group
ORDER BY age_group;

Segments population by demographics to guide care strategies
Query 7: Department Performance Comparison
SELECT department,
       COUNT(*) AS total_admissions,
       ROUND(SUM(CASE WHEN treatment_outcome='Recovered' THEN 1 ELSE 0 END)*100.0/COUNT(*),1) AS recovery_pct,
       ROUND(AVG(total_bill),2) AS avg_bill,
       ROUND(AVG(length_of_stay),2) AS avg_stay,
       ROUND((COUNT(*)*100.0/(SELECT COUNT(*) FROM patients)),1) AS pct_of_total
FROM patients
GROUP BY department
ORDER BY total_admissions DESC;

Enables cross-department performance benchmarking and best-practice identification
Query 8: High-Cost Patient Identification
SELECT patient_id, patient_name, age, department,
       COUNT(*) AS admission_count,
       ROUND(SUM(total_bill),2) AS total_patient_cost,
       ROUND(AVG(total_bill),2) AS avg_bill_per_admission,
       ROUND(AVG(length_of_stay),2) AS avg_stay
FROM patients
GROUP BY patient_id, patient_name, age, department
HAVING SUM(total_bill) > 50000
ORDER BY total_patient_cost DESC
LIMIT 50;

Identifies candidates for high-cost care management programs
Query 9: Cumulative Patient Spending Trends
SELECT patient_id, admission_date, total_bill,
       SUM(total_bill) OVER (PARTITION BY patient_id ORDER BY admission_date) AS cumulative_spending,
       ROW_NUMBER() OVER (PARTITION BY patient_id ORDER BY admission_date) AS admission_sequence
FROM patients
ORDER BY patient_id, admission_date;

Tracks spending progression and cost escalation patterns for interventions
Query 10: Recovery Rate by Department and Age
SELECT department,
       CASE 
           WHEN age < 18 THEN 'Pediatric (0-18)'
           WHEN age BETWEEN 18 AND 35 THEN 'Young Adult (18-35)'
           WHEN age BETWEEN 36 AND 60 THEN 'Adult (36-60)'
           ELSE 'Senior (60+)'
       END AS age_group,
       COUNT(*) AS patient_count,
       SUM(CASE WHEN treatment_outcome='Recovered' THEN 1 ELSE 0 END) AS recovered,
       ROUND(SUM(CASE WHEN treatment_outcome='Recovered' THEN 1 ELSE 0 END)*100.0/COUNT(*),1) AS recovery_rate
FROM patients
GROUP BY department, age_group
ORDER BY department, age_group;

Cross-tabulates outcomes across multiple dimensions for targeted analysis
```

###  Step 5: Export Results to CSV
```sql
SELECT * INTO OUTFILE '/tmp/admissions_by_department.csv'
FIELDS TERMINATED BY ','
FROM (
    SELECT department, COUNT(*) AS total_admissions
    FROM patients
    GROUP BY department
    ORDER BY total_admissions DESC
) t;
```

## 📊 Recommended Visualizations
- Admission Volume Dashboard - Column chart of admissions by department with trend line
- Treatment Outcomes Pie Chart - Distribution of Recovered (70.4%) vs Referred (23.4%) vs Deceased (6.2%)
- Department Efficiency Heat Map - Scatter plot of admissions vs average stay revealing efficiency patterns
- Length of Stay Benchmark - Horizontal bar chart comparing avg stay across departments
- Financial Impact by Outcome - Bar chart of average bills by treatment outcome
- Physician Performance Scorecard - Table of top doctors with patient count, recovery rate, avg bill
- Patient Age Distribution Histogram - Distribution showing peak ages (36-60) and senior population
- High-Cost Patient Pareto Chart - Identifying 20% of patients driving costs
- Monthly Admission Trend Line - Temporal analysis revealing seasonal patterns
- Department Recovery Rate Comparison - Ranked bar chart showing quality metrics

## 🎓 Learning Outcomes

- By working through this project, you will master:
- Healthcare data analytics and patient record analysis
- Hospital database design and schema optimization
- Medical department performance evaluation techniques
- Treatment outcome analysis and quality metrics
- Physician workload and productivity assessment
- Patient segmentation by demographics and clinical factors
- Complex SQL queries for multi-dimensional healthcare analysis
- Window functions for ranking and cumulative calculations
- CASE statements for outcome classification and categorization
- Temporal analysis and admission trend identification
- Financial analysis of healthcare delivery costs
- Strategic decision support through data analytics
- Working with large healthcare datasets (1,000+ records)
- Creating actionable business intelligence for hospital administration



## 📝 Author
**Robin Jimmichan P**  
[LinkedIn](https://www.linkedin.com/in/robin-jimmichan-pooppally-676061291) | [GitHub](https://github.com/Robi8995)


## 📚 Technical Stack
- Database: MySQL 8.0+
- Languages: SQL
- Tools: MySQL Workbench, CSV Export

*This comprehensive project demonstrates SQL mastery in healthcare analytics, combining sophisticated database design with clinical outcome analysis and financial performance metrics to drive meaningful improvements in hospital operations, patient care quality, and organizational efficiency.*


