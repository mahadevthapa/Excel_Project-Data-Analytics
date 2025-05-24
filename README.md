# Excel Salary Dashboard & Job Market Analysis

## Introduction

This Excel-based project focuses on analyzing salaries in the data job market and identifying key insights for job seekers and professionals. The dashboard and analysis were built using Excel features such as Pivot Tables, Charts, Power Query, and DAX to derive valuable trends from real-world job data.

The goal is to enable users to understand how various factors like job title, region, and skills influence salaries, helping them make better career decisions.

### Dashboard File

## Project 1: Excel Salary Dashboard

### Excel Skills Used

* **📉 Charts**
* **🧮 Formulas and Functions**
* **❎ Data Validation**

### Dataset

The data consists of job postings from 2023, including:

* 👨‍💼 Job Titles
* 💰 Salaries
* 📍 Locations
* 🛠️ Required Skills

---

### 📊 Salary Insights by Job Title (Bar Chart)

* Utilized horizontal bar charts to compare median salaries.
* Sorted job titles in descending order of salary.
* Key insight: Senior-level roles and Engineers generally earn more than Analyst roles.

### 🗺️ Country Median Salaries (Map Chart)

* Used Excel Map Charts to show geographical salary distribution.
* Regions are color-coded for easy interpretation.
* Insight: Notable salary disparities exist across different countries.

### 🧮 Median Salary Formula

```excel
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

* Returns median salary based on multiple filters: job title, country, and schedule type.

### ⏰ Count of Job Schedule Type

```excel
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

* Filters list to get unique job schedule types by removing invalid entries.

### ❎ Data Validation

* Implemented dropdowns for selecting validated inputs like `Job Title`, `Country`, and `Schedule Type`.
* Prevents incorrect or inconsistent entries, improving dashboard usability.

<img src="/images/one.png" width="750" height="500" alt="Salary Dashboard Chart1">

---

## Project 2: Job Market Skills & Salary Analysis

### Excel Skills Used

* 📊 Pivot Tables
* 📈 Pivot Charts
* 🧮 DAX (Data Analysis Expressions)
* 🔍 Power Query
* 💪 Power Pivot

### Questions Analyzed

1. Do more skills lead to better pay?
2. What's the salary for data jobs across regions?
3. What are the top skills in demand?
4. What do the top-paying skills look like?

---

## 1️⃣ Do More Skills Get You Better Pay?

### 🔍 Power Query Steps

* Extracted and cleaned data using Power Query.
* Split into two datasets: `data_jobs_all` and `data_job_skills`.


### 💡 Insight

* Positive correlation between number of skills and salary.
* Senior roles requiring more skills often offer higher salaries.

<img src="/images/six.png" width="850" height="550" alt="Salary Dashboard Chart1">

<img src="/images/two.png" width="850" height="550" alt="Salary Dashboard Chart1">

---

## 2️⃣ Salaries Across Regions

### 🧮 DAX and PivotTable

```dax
=CALCULATE(
    MEDIAN(data_jobs_all[salary_year_avg]),
    data_jobs_all[job_country] = "United States"
)
```

### 💡 Insight

* US-based roles generally offer higher salaries.
* Regional salary comparisons reveal economic and industry differences.

<img src="/images/three.png" width="850" height="550" alt="Salary Dashboard Chart1">

---

## 3️⃣ Top Skills in the Data Job Market

### 💪 Power Pivot Data Model

* Created relationships using `job_id` between job and skills datasets.
* Integrated cleaned data for detailed analysis.

### 💡 Insight

* Python, SQL, AWS, and Azure are the most in-demand and high-paying skills.

<img src="/images/nine.png" width="850" height="550" alt="Salary Dashboard Chart1">

<img src="/images/seven.png" width="850" height="550" alt="Salary Dashboard Chart1">

<img src="/images/four.png" width="850" height="550" alt="Salary Dashboard Chart1">


---

## 4️⃣ Salary of Top 10 Skills

### 📈 PivotChart (Combo)

* Clustered column chart for salaries.
* Line with markers for skill likelihood.


### 💡 Insight

* Python, SQL, and Oracle lead in salary potential.
* Less technical skills like Word and PowerPoint show low pay and low demand.

<img src="/images/five.png" width="850" height="450" alt="Salary Dashboard Chart1">

---

## Conclusion

These Excel projects provided comprehensive insights into the data job market. By combining charting, Power Query, PivotTables, and DAX, I could analyze how job roles, locations, and skills impact salaries.

The dashboards are designed for clarity, helping both job seekers and professionals explore trends and make informed career decisions. Acquiring the right combination of technical skills can significantly improve salary potential in today's data-driven world.
