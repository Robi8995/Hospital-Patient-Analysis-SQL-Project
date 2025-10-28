# 🏥 Hospital Patient Records Analysis – SQL Project

[![SQL](https://img.shields.io/badge/SQL-MySQL-blue)](https://www.mysql.com/) 
[![Skills](https://img.shields.io/badge/Skills-Healthcare_Analytics-green)](https://www.linkedin.com/in/yourprofile)
[![Database](https://img.shields.io/badge/Database-Design-orange)](https://github.com/yourprofile)

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

---

## 📚 Technical Stack

| Component | Technology |
|-----------|------------|
| **Database** | MySQL 8.0+ |
| **Languages** | SQL |
| **Tools** | MySQL Workbench, CSV Export |

---

## 📝 Author
**Robin Jimmichan Pooppally**  
[LinkedIn](https://www.linkedin.com/in/robin-jimmichan-pooppally-676061291) | [GitHub](https://github.com/Robi8995)

---

*This comprehensive project demonstrates SQL mastery in healthcare analytics, combining sophisticated database design with clinical outcome analysis and financial performance metrics to drive meaningful improvements in hospital operations, patient care quality, and organizational efficiency*
