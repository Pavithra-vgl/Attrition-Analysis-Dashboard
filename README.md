# Attrition Analysis Dashboard

## Overview
This Power BI dashboard provides a comprehensive analysis of employee attrition, focusing on key metrics such as attrition rate, employee satisfaction, and demographic breakdowns. Each visual is designed to highlight specific insights, making it easier to identify patterns and areas of concern.

---

## Dashboard Visuals and Cards

### 1. **Top Summary Cards (KPI Cards)**
   - **Employees**: Displays the total number of employees.
     - **Field Used**: `COUNTROWS(Table1)`
   - **Employees Quit**: Shows the total count of employees who have left the organization.
     - **Field Used**: `COUNTROWS(FILTER(Table1, Table1[Attrition] = "Yes"))`
   - **Attrition %**: Displays the attrition percentage, calculated as a percentage of employees who have left.
     - **DAX Measure**:
       ```DAX
       Attrition % = DIVIDE(COUNTROWS(FILTER(Table1, Table1[Attrition] = "Yes")), COUNTROWS(Table1)) * 100
       ```
   - **Active Employees**: Shows the count of current employees.
     - **Field Used**: `COUNTROWS(FILTER(Table1, Table1[Attrition] = "No"))`
   - **Average Age**: Displays the average age of all employees.
     - **Field Used**: `AVERAGE(Table1[Age])`
   - **Formatting**: Each card is color-coded for visual emphasis and easy readability.

### 2. **Attrition by Department (Pie Chart)**
   - **Description**: A pie chart showing the distribution of attrition by department.
   - **Columns Used**:
     - `Department`: Represents each department (e.g., R&D, Sales, HR).
     - `Count of Attrition`: Calculates the number of employees who left in each department.
   - **Conditional Formatting**: Each department is represented with a unique color for easy differentiation.

### 3. **Attrition by Age Group and Gender (Clustered Column Chart)**
   - **Description**: Displays attrition counts across age groups, segmented by gender.
   - **Columns Used**:
     - `Age Band`: Groups employees into age ranges (e.g., 25-34, 35-44, 45-54, etc.).
     - `Gender`: Differentiates attrition counts by gender within each age group.
     - `Count of Attrition`: Total count of attrition in each age group and gender segment.
   - **Formatting**: The bars are segmented by color to distinguish male and female attrition counts within each age group.

### 4. **Work Life Balance by Job Role (Matrix/Heatmap)**
   - **Description**: A heatmap matrix that shows the distribution of work-life balance ratings across different job roles.
   - **Columns Used**:
     - `Job Role`: Lists various job roles (e.g., Healthcare Representative, Human Resources, Manager).
     - `Work Life Balance Rating`: Columns represent different ratings from 1 to 4.
     - `Count of Employees`: Displays the count of employees for each rating within each job role.
   - **Conditional Formatting**: Cells are color-coded from light to dark based on employee count, with higher counts represented in darker shades, helping to visually emphasize areas with higher/lower work-life balance ratings.

### 5. **Job Satisfaction (Gauge Chart)**
   - **Description**: A gauge chart that visualizes the average job satisfaction rating across the organization.
   - **Columns Used**:
     - `Job Satisfaction`: Displays a score ranging from 0 to 5.46.
     - `Average Satisfaction Score`: The calculated average job satisfaction score.
   - **Formatting**: The gauge uses a gradient fill with a distinct color for the actual value, making it clear where the average satisfaction score stands within the range.

### 6. **Attrition by Education (Bar Chart)**
   - **Description**: A bar chart displaying the count of attrition by different educational fields.
   - **Columns Used**:
     - `Education Field`: Lists fields like Life Sciences, Medical, Marketing, Technical Degree, etc.
     - `Count of Attrition`: Shows the number of employees who have left from each educational field.
   - **Formatting**: Bars are color-coded, with larger bars representing fields with higher attrition counts.

### 7. **Attrition by Age Group (Donut Chart)**
   - **Description**: A donut chart visualizing the distribution of attrition by age group.
   - **Columns Used**:
     - `Age Group`: Segments employees into age bands (e.g., 18-24, 25-34, etc.).
     - `Gender`: Inner segments represent gender distribution within each age group.
     - `Count of Attrition`: Total number of employees who have left within each age group.
   - **Conditional Formatting**: Age groups are assigned distinct colors, and segments for male and female are clearly differentiated for easy analysis.

---


