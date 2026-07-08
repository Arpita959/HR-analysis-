# 📊 HR Analytics Dashboard — Power BI & SQL

## 📌 Project Overview

This project presents a comprehensive **HR Analytics Dashboard** built using **Power BI** and **SQL** to analyse employee data, uncover workforce trends, and support data-driven HR decision-making.

The analysis covers key HR metrics including employee attrition, department-wise performance, salary distribution, job satisfaction, and demographic insights — enabling HR teams and management to identify patterns and take proactive action.

---

## 🎯 Business Problem

HR departments often struggle to:
- Identify **why employees leave** (attrition analysis)
- Understand **which departments** have the highest turnover
- Analyse **salary vs performance** relationships
- Track **employee satisfaction** across roles and age groups
- Make **data-backed workforce decisions**

This project solves these problems by transforming raw HR data into **interactive visualisations and SQL-driven insights**.

---

## 📁 Repository Structure

```
HR-analysis/
│
├── HR_Analytics.csv                          # Raw HR dataset
├── HR Dashbaord.pbix                         # Power BI Dashboard file
├── HR Dashbaord.pdf                          # Dashboard PDF export
├── SQLQuery1.sql                             # SQL queries for HR analysis
├── SQL Questions Based on HR Analytics       # SQL question set
│   Dataset.pdf
└── README.md                                 # Project documentation
```

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **Power BI** | Interactive dashboard & data visualisation |
| **SQL** | Data extraction, manipulation & analysis |
| **Microsoft Excel / CSV** | Data storage & preprocessing |
| **DAX** | Calculated measures & KPIs in Power BI |

---

## 📊 Dataset Overview

**File:** `HR_Analytics.csv`

The dataset contains employee-level HR data with the following key attributes:

| Column | Description |
|--------|-------------|
| `EmpID` | Unique Employee ID |
| `Age` | Employee Age |
| `Department` | Department Name |
| `JobRole` | Job Role/Title |
| `Gender` | Employee Gender |
| `Education` | Education Level |
| `MonthlyIncome` | Monthly Salary |
| `JobSatisfaction` | Satisfaction Score (1–4) |
| `Attrition` | Whether employee left (Yes/No) |
| `YearsAtCompany` | Tenure in years |
| `PerformanceRating` | Performance Score |
| `WorkLifeBalance` | Work-life balance rating |
| `OverTime` | Whether employee works overtime |

---

## 🔍 Key Analysis & Insights

### 📉 Attrition Analysis
- Identified **overall attrition rate** across the organisation
- Analysed attrition by **department, age group, job role, and salary band**
- Determined that employees with **lower salary and high overtime** had significantly higher attrition

### 👥 Demographic Insights
- Analysed **age distribution** and its correlation with job satisfaction
- Gender-wise breakdown of roles and salary levels
- Education level vs monthly income analysis

### 💰 Salary & Performance
- Compared **monthly income across job roles** and departments
- Identified salary gaps and **high-performing but underpaid** employee segments
- Analysed relationship between **performance rating and salary hike**

### 😊 Job Satisfaction
- Tracked **satisfaction scores by department and role**
- Identified roles with **lowest satisfaction** — actionable for HR intervention
- Correlated overtime hours with work-life balance ratings

---

## 📈 Power BI Dashboard Features

The interactive Power BI dashboard (`HR Dashbaord.pbix`) includes:

- ✅ **KPI Cards** — Total Employees, Attrition Rate, Average Salary, Average Tenure
- ✅ **Attrition by Department** — Bar chart showing turnover per department
- ✅ **Age Group Analysis** — Distribution of employees and attrition by age
- ✅ **Job Role Breakdown** — Salary and satisfaction per role
- ✅ **Gender Distribution** — Pie chart with department filter
- ✅ **Monthly Income vs Performance** — Scatter/bar analysis
- ✅ **Interactive Slicers** — Filter by Department, Gender, Education, Job Role
- ✅ **Work-Life Balance Heatmap** — Satisfaction vs overtime correlation

---

## 🗄️ SQL Analysis

**File:** `SQLQuery1.sql`

Key SQL queries written for this project:

```sql
-- 1. Overall Attrition Rate
SELECT 
    COUNT(*) AS TotalEmployees,
    SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) AS AttritionCount,
    ROUND(SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) * 100.0 / COUNT(*), 2) AS AttritionRate
FROM HR_Analytics;

-- 2. Attrition by Department
SELECT 
    Department,
    COUNT(*) AS TotalEmployees,
    SUM(CASE WHEN Attrition = 'Yes' THEN 1 ELSE 0 END) AS AttritionCount
FROM HR_Analytics
GROUP BY Department
ORDER BY AttritionCount DESC;

-- 3. Average Salary by Job Role
SELECT 
    JobRole,
    ROUND(AVG(MonthlyIncome), 2) AS AvgSalary,
    COUNT(*) AS EmployeeCount
FROM HR_Analytics
GROUP BY JobRole
ORDER BY AvgSalary DESC;

-- 4. Job Satisfaction by Department
SELECT 
    Department,
    ROUND(AVG(JobSatisfaction), 2) AS AvgSatisfaction
FROM HR_Analytics
GROUP BY Department
ORDER BY AvgSatisfaction;
```

---

## 💡 Key Findings

1. **Attrition is highest** in the Sales and R&D departments
2. Employees earning **below average salary with overtime** are 3x more likely to leave
3. **Age group 26–35** shows the highest attrition — early career mobility
4. **Job satisfaction scores below 2** strongly correlate with employee exits
5. Employees with **more than 5 years tenure** show significantly lower attrition

---

## 🚀 How to Use This Project

### View the Dashboard
1. Download `HR Dashbaord.pbix`
2. Open with **Power BI Desktop** (free download at powerbi.microsoft.com)
3. Explore interactive filters and visuals

### Run the SQL Queries
1. Import `HR_Analytics.csv` into **MySQL / SQL Server / PostgreSQL**
2. Open `SQLQuery1.sql`
3. Execute queries to reproduce the analysis

### View PDF Report
- Open `HR Dashbaord.pdf` for a static version of the dashboard

---

## 📚 Learnings & Skills Demonstrated

- ✅ Data cleaning and preprocessing using SQL
- ✅ Advanced SQL queries — joins, aggregations, window functions, CASE statements
- ✅ Power BI dashboard development with DAX measures
- ✅ Data visualisation best practices
- ✅ HR domain knowledge — attrition, satisfaction, performance metrics
- ✅ Stakeholder-ready reporting and data storytelling

---

## 👩‍💻 Author

**Arpita Kumari**
- 🔗 [LinkedIn](https://linkedin.com/in/arpita-kumari-appy)
- 💻 [GitHub](https://github.com/Arpita959)
- 📧 arpita04appy@gmail.com

---

## ⭐ If you found this project helpful, please give it a star!

---

*Built with 💙 using Power BI & SQL*
