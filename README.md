# 📊 Nexora HR Analytics Dashboard — Power BI

## 📌 Project Overview

The **Nexora HR Analytics Dashboard** is an interactive HR analytics project developed using **Microsoft Power BI**.

The dashboard provides a clear view of employee attrition, workforce distribution, salary patterns, department-level analysis, job roles, age groups, and other important HR metrics.

The project uses **Power BI, DAX, KPIs, interactive slicers, data visualization, and drill-through analysis** to transform raw employee data into meaningful business insights.

> **Note:** The project uses the existing HR employee dataset for analysis, presented in a Nexora company context.

---

## 🎯 Project Objectives

The main objectives of this project are:

* Analyze overall employee attrition.
* Identify departments with higher employee turnover.
* Analyze attrition by gender and job role.
* Understand employee distribution across different age groups.
* Analyze average monthly income across departments.
* Compare department-level employee retention.
* Create interactive KPIs for important HR metrics.
* Provide drill-through analysis for detailed employee information.
* Help HR teams identify areas that may require better employee retention strategies.

---

## 🛠️ Tools & Technologies

| Tool / Technology       | Purpose                                   |
| ----------------------- | ----------------------------------------- |
| **Microsoft Power BI**  | Dashboard development and visualization   |
| **DAX**                 | Measures and calculations                 |
| **Power Query**         | Data cleaning and transformation          |
| **Excel / CSV Dataset** | Source employee data                      |
| **GitHub**              | Project documentation and version control |

---

## 📈 Dashboard Preview

### 🏢 Main Nexora HR Dashboard

The dashboard contains interactive KPIs, charts, department analysis, employee attrition analysis, and filters.

**📸 Add your dashboard screenshot below:**

![Nexora HR Analytics Dashboard](images/Dashboard_Img.png.png)

> **How to add the screenshot:** Upload your dashboard image to the same GitHub repository and name it `Dashboard_Img.png`. If you use a different filename, replace `Dashboard_Img.png` in the image link above.

---

## 📊 Key Performance Indicators (KPIs)

The dashboard contains the following important KPIs:

| KPI                        | Description                                        |
| -------------------------- | -------------------------------------------------- |
| **Total Employees**        | Total number of employees in the organization      |
| **Employees Left**         | Number of employees who left the organization      |
| **Active Employees**       | Number of employees currently remaining            |
| **Attrition Rate**         | Percentage of employees who left the organization  |
| **Average Monthly Income** | Average monthly income of employees                |
| **Average Age**            | Average age of employees                           |
| **Average Experience**     | Average years employees have worked at the company |

---

## 📉 Dashboard Analysis

### 1. Employee Attrition by Department

This visual compares the number of employees who left across different departments.

It helps identify departments with higher employee turnover and areas where HR may need to focus on employee retention.

### 2. Employee Attrition by Gender

This analysis compares employee attrition between male and female employees.

It helps identify differences in employee turnover across gender groups.

### 3. Employee Attrition by Job Role

This visual identifies job roles with higher numbers of employees leaving the organization.

It can help HR investigate possible issues related to workload, career growth, compensation, or employee satisfaction.

### 4. Average Salary by Department

This visual compares the average monthly income across departments.

It helps provide an overview of salary patterns between departments.

### 5. Total Employees by Age Group

Employees are grouped into different age categories to understand workforce distribution.

The dashboard uses groups such as:

* Under 30
* 30–39
* 40–49
* 50+

### 6. Department Performance

Because the dataset does not contain a direct employee performance rating, department performance is represented using **employee retention**.

A department with lower attrition has a higher retention percentage.

This provides an indication of workforce stability rather than a direct employee performance score.

---

## 🧮 DAX Measures

The project uses DAX measures to calculate important HR metrics.

### Total Employees

```DAX
Total Employees = COUNTROWS(Employee)
```

Counts the total number of employee records.

### Employees Left

```DAX
Employees Left =
CALCULATE(
    COUNTROWS(Employee),
    Employee[Attrition] = "Yes"
)
```

Counts employees whose attrition status is **Yes**.

### Active Employees

```DAX
Active Employees =
[Total Employees] - [Employees Left]
```

Calculates the number of employees who are still working.

### Attrition Rate

```DAX
Attrition Rate =
DIVIDE(
    [Employees Left],
    [Total Employees],
    0
)
```

Calculates the percentage of employees who left the organization.

### Average Monthly Income

```DAX
Average Monthly Income =
AVERAGE(Employee[MonthlyIncome])
```

Calculates the average monthly income.

### Average Age

```DAX
Average Age =
AVERAGE(Employee[Age])
```

Calculates the average employee age.

### Average Experience

```DAX
Average Experience =
AVERAGE(Employee[YearsAtCompany])
```

Calculates the average number of years employees have worked at the company.

### Department Performance

```DAX
Department Performance =
1 -
DIVIDE(
    CALCULATE(
        COUNTROWS(Employee),
        Employee[Attrition] = "Yes"
    ),
    COUNTROWS(Employee)
)
```

Calculates department retention by subtracting the department's attrition rate from 100%.

---

## 🧩 Calculated Column

### Age Group

Employees are categorized into different age groups to make age-based analysis easier.

```DAX
Age Group =
SWITCH(
    TRUE(),
    Employee[Age] < 30, "Under 30",
    Employee[Age] >= 30 && Employee[Age] <= 39, "30 - 39",
    Employee[Age] >= 40 && Employee[Age] <= 49, "40 - 49",
    "50+"
)
```

---

## 🔍 Drill-Through Analysis

The project includes a **Power BI drill-through page** for detailed employee-level analysis.

Users can select a department from the main dashboard and navigate to the drill-through page to examine detailed employee information.

The drill-through analysis can include:

* Job Role
* Monthly Income
* Attrition
* Age
* Gender
* Department

This allows users to move from a high-level department view to more detailed employee-level information.

---

## 🎛️ Interactive Features

The dashboard includes:

* 📌 KPI Cards
* 📊 Interactive Charts
* 🔎 Department Filters
* 👥 Gender Filters
* 🎂 Age Group Filters
* 🔄 Cross-filtering
* 🔍 Drill-through Analysis
* 📈 Department Comparison
* 📊 Attrition Analysis

These features allow users to explore the data dynamically rather than viewing only static reports.

---

## 💡 Key Insights

The analysis provides several important HR insights:

* Employee attrition can be monitored using the overall attrition rate.
* Certain departments experience higher employee turnover than others.
* Some job roles have considerably higher attrition than others.
* Employee turnover can be compared across gender and age groups.
* Salary patterns vary between departments.
* Age-group analysis helps understand the organization's workforce structure.
* Department retention can be used to identify areas with greater workforce stability.

---

## 🎯 Business Recommendations

Based on the analysis, HR teams can:

1. Investigate departments with higher attrition.
2. Analyze job roles with consistently high employee turnover.
3. Review employee compensation and career-growth opportunities.
4. Develop targeted employee retention strategies.
5. Monitor attrition regularly using HR dashboards.
6. Use employee demographics to understand workforce trends.
7. Identify stable departments and learn from their retention practices.

---

## 📁 Project Structure

```text
Nexora-HR-Analytics-Dashboard/
│
├── 📊 Nexora_HR_Analytics_Dashboard.pbix
├── 🖼️ Dashboard_Img.png
├── 📄 README.md
└── 📜 LICENSE
```

---

## 🚀 How to Use the Project

1. Download or clone this repository.
2. Open the `.pbix` file using **Microsoft Power BI Desktop**.
3. Explore the main dashboard.
4. Use the available filters and slicers.
5. Select departments to interact with the visuals.
6. Use the drill-through functionality for detailed analysis.

---

## 📚 Skills Demonstrated

Through this project, the following skills were demonstrated:

* Power BI Dashboard Development
* Data Visualization
* DAX
* KPI Development
* Data Cleaning
* Data Transformation
* HR Analytics
* Attrition Analysis
* Interactive Filtering
* Drill-Through Reports
* Business Insights
* Data Storytelling

---

## 👨‍💻 Project

**Project:** Nexora HR Analytics Dashboard
**Domain:** Human Resources Analytics
**Tool:** Microsoft Power BI
**Focus:** Employee Attrition & Workforce Analysis

---

## ⭐ Conclusion

The Nexora HR Analytics Dashboard transforms employee data into an interactive analytical report that helps understand workforce trends, employee attrition, department stability, salary patterns, and demographic distribution.

The project demonstrates how **Power BI and DAX can be used to convert raw HR data into meaningful insights that support data-driven HR decision-making.**
Created By TUHIN
