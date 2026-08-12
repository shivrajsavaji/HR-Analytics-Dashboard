# HR-Analytics-Dashboard

## Project Overview

This project presents a complete end-to-end HR analytics dashboard built on Tableau,
analyzing workforce data for a company of 1,470 employees. The objective is to help
the HR team identify attrition patterns, understand workforce demographics, evaluate
job satisfaction, and build targeted retention strategies using data-driven insights.

The project follows the full analyst workflow:

```
Raw HR Data --> Data Cleaning --> Tableau Dashboard --> GitHub
```

---

## Problem Statement

The HR department faces five key workforce challenges that this analysis addresses:

| Area | Business Question |
|------|-------------------|
| Attrition Analysis | Which departments and age groups are losing the most employees? |
| Gender Insights | How does attrition differ across male and female employees? |
| Demographic Profile | What is the age distribution of the current workforce? |
| Job Satisfaction | Which roles have the highest and lowest satisfaction ratings? |
| Education Background | Which educational fields show the highest attrition risk? |

---

## Dataset Description

| Column | Description |
|--------|-------------|
| Employee ID | Unique identifier for each employee |
| Department | Employee's department — HR, R&D, or Sales |
| Age | Age of the employee |
| Gender | Male or Female |
| Education Field | Educational background — Life Sciences, Medical, Marketing etc. |
| Job Role | Role title — Sales Executive, Lab Technician, Manager etc. |
| Job Satisfaction | Rating from 1 (very dissatisfied) to 4 (very satisfied) |
| Attrition | Whether the employee left the company — Yes or No |
| Age Group | Binned age category — Under 25, 25–34, 35–44, 45–54, Over 55 |

Source: HR Analytics Dataset | 1,470 employees

---

## Tableau Dashboard

### Layout Structure

The dashboard uses a dark-themed professional layout with the following structure:

```
+----------------------------------------------------------+----------+
|   KPI Cards (5 cards — Employee Count, Attrition Rate,  | Attrition|
|   Attrition Count, Active Employees, Avg. Age)          | by Gender|
+---------------------+--------------------+---------------+----------+
|  Department Wise    |  No of Employees   |  Job Satisfaction Rating |
|  Attrition          |  by Age Group      |  (Matrix / Heatmap)      |
|  (Pie Chart)        |  (Bar Chart)       |                          |
+---------------------+--------------------+--------------------------+
|  Education Field Wise Attrition  |  Attrition Rate by Gender        |
|  (Horizontal Bar Chart)          |  for Different Age Groups        |
|                                  |  (Donut Charts x 5)              |
+----------------------------------+----------------------------------+
```

---

### KPI Cards

Five summary KPI metrics are displayed at the top of the dashboard:

| Metric | Value | Description |
|--------|-------|-------------|
| Employee Count | 1,470 | Total employees (current + left) |
| Attrition Rate | 16.12% | Percentage of employees who left |
| Attrition Count | 237 | Exact number of employees who left |
| Active Employees | 1,233 | Currently working employees (1470 − 237) |
| Avg. Age | 37 | Average age across all employees |

---

### Chart 1 — Department Wise Attrition (Pie Chart)

- Type: Pie chart
- Field: Department (HR, R&D, Sales)
- Shows which department contributes most to total attrition

| Department | Employees Left | Percentage |
|------------|----------------|------------|
| R&D | 133 | 56.12% |
| HR | 92 | 38.82% |
| Sales | 12 | 5.06% |

Insight: R&D accounts for over half of all attrition. This department requires
urgent investigation into workload, compensation, and growth opportunities.

---

### Chart 2 — No of Employees by Age Group (Bar Chart)

- Type: Vertical bar chart
- X-axis: Age (18 to 60, binned by 3)
- Y-axis: Employee count
- Bin size: 3

| Age Range | Employee Count |
|-----------|---------------|
| 18–20 | 28 |
| 21–23 | 43 |
| 24–26 | 91 |
| 27–29 | 164 |
| 30–32 | 190 |
| 33–35 | 213 (peak) |
| 36–38 | 177 |
| 39–41 | 139 |
| 42–44 | 111 |
| 45–47 | 98 |
| 48–50 | 73 |
| 51–53 | 56 |
| 54–56 | 54 |
| 57–59 | 28 |
| 60+ | 5 |

Insight: The 30–36 age group is the largest workforce segment. Employee count
drops sharply after age 54, indicating early attrition or retirement in senior years.

---

### Chart 3 — Job Satisfaction Rating (Matrix / Heatmap)

- Type: Crosstab matrix table
- Rows: Job Role
- Columns: Satisfaction Rating (1, 2, 3, 4) + Grand Total
- Rating scale: 1 = Very Dissatisfied → 4 = Very Satisfied

| Job Role | Rating 1 | Rating 2 | Rating 3 | Rating 4 | Total |
|----------|----------|----------|----------|----------|-------|
| Healthcare Representative | 26 | 19 | 43 | 43 | 131 |
| Human Resources | 10 | 16 | 13 | 13 | 52 |
| Laboratory Technician | 56 | 48 | 75 | 80 | 259 |
| Manager | 21 | 21 | 27 | 33 | 102 |
| Manufacturing Director | 26 | 32 | 49 | 38 | 145 |
| Research Director | 15 | 16 | 27 | 22 | 80 |
| Research Scientist | 54 | 53 | 90 | 95 | 292 |
| Sales Executive | 69 | 54 | 91 | 112 | 326 |
| Sales Representative | 12 | 21 | 27 | 23 | 83 |
| **Grand Total** | **289** | **280** | **442** | **459** | **1,470** |

Insight: Sales Executive is the largest role (326 employees). Lab Technician has
the highest dissatisfaction — 56 employees rated 1. Overall, rating 4 is the most
common with 459 employees, which is a positive workforce signal.

---

### Chart 4 — Education Field Wise Attrition (Horizontal Bar Chart)

- Type: Horizontal bar chart
- X-axis: Number of employees who left
- Y-axis: Education field
- Sorted: Descending by attrition count

| Education Field | Employees Left |
|----------------|---------------|
| Life Sciences | 89 |
| Medical | 63 |
| Marketing | 35 |
| Technical Degree | 32 |
| Other | 11 |
| Human Resources | 7 |

Insight: Life Sciences and Medical backgrounds together account for 64% of all
attrition. This directly correlates with the high R&D department attrition seen above.

---

### Chart 5 — Attrition Rate by Gender for Different Age Groups (Donut Charts)

- Type: 5 donut charts (one per age group)
- Color coding: Yellow = Female, Green = Male
- Shows male vs female attrition split within each age group

| Age Group | Total Left | Male | Female |
|-----------|-----------|------|--------|
| Under 25 | 38 | 20 (8.44%) | 18 (7.59%) |
| 25–34 | 112 | 69 (29.11%) | 43 (18.14%) |
| 35–44 | 51 | 37 (15.61%) | 14 (5.91%) |
| 45–54 | 25 | 16 (6.75%) | 9 (3.80%) |
| Over 55 | 11 | 8 (3.38%) | 3 (1.27%) |

Insight: The 25–34 age group is the most at-risk segment with 112 departures.
Males leave at a significantly higher rate in every age group, especially 25–34 and 35–44.

---

### Chart 6 — Attrition by Gender (Bar Chart)

- Type: Horizontal bar chart
- Positioned top-right corner
- Simple male vs female total attrition comparison

| Gender | Employees Left |
|--------|---------------|
| Male | 150 |
| Female | 87 |

Insight: Males account for 63% of total attrition vs 37% for females.

---

### Interactive Filter

| Filter | Field | Purpose |
|--------|-------|---------|
| Education Field | Education background | Filters all visuals by employee education field |

---

## Key Findings Summary

### Attrition Overview
- Total attrition rate of 16.12% — significantly above the industry benchmark of ~10%
- 237 out of 1,470 employees have left the organization
- Males account for 150 departures (63%) vs females at 87 (37%)

### Department Insights
- R&D is the most affected department — 133 employees left (56% of all attrition)
- Sales has the lowest attrition with only 12 departures (5%)
- HR sits in the middle with 92 departures (38.82%)

### Age and Demographics
- Largest workforce segment: ages 30–36 (peak at 33–35 with 213 employees)
- Highest attrition age group: 25–34 with 112 employees leaving
- Workforce count drops sharply after age 54

### Job Satisfaction
- Sales Executive (326 employees) is the largest role — 112 employees gave top rating
- Lab Technician has the highest dissatisfaction — 56 employees rated 1 (very unhappy)
- Grand total shows rating 4 is the most common — 459 employees are very satisfied

### Education Background
- Life Sciences (89) and Medical (63) show the highest attrition counts
- Human Resources background has the lowest attrition with only 7 employees leaving

---

## Recommendations

1. **Address R&D attrition urgently** — over half of all exits come from R&D; conduct
   stay interviews and review compensation, career growth, and workload balance

2. **Retain the 25–34 age group** — 112 departures from this group; introduce
   mid-career development programs, mentoring, and internal mobility opportunities

3. **Improve Lab Technician satisfaction** — 56 employees gave the lowest rating;
   review role responsibilities, recognition programs, and compensation benchmarks

4. **Target Life Sciences and Medical professionals** — these two groups account for
   64% of all attrition; build education-specific retention and engagement strategies

5. **Focus on male employee engagement** — males leave at nearly double the rate of
   females; investigate workload, work-life balance, and career stagnation factors

6. **Build a predictive retention model** — combine age group, department, education
   field, and satisfaction score to proactively flag at-risk employees before they resign

---

## Tools and Technologies

| Tool | Version | Purpose |
|------|---------|---------|
| Tableau Desktop | Latest | Dashboard design and interactive visualizations |
| Tableau Public | Latest | Publishing and portfolio sharing |
| Excel / CSV | - | Raw HR data preparation and source |
| GitHub | - | Version control and portfolio hosting |

---
