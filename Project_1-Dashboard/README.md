# Excel Salary Dashboard

![1_Salary_Dashboard.png](/0_Resources/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This data jobs salary dashboard was created to help job seekers investigate salaries for their desired jobs and ensure they are being adequately compensated. 

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023, containing key information including:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

###  Charts

####  Data Job Salaries - Bar Chart

<img src="/0_Resources/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

- **Chart/table Features:** Utilized the bar chart feature, formatting the salaries and optimized the layout for clarity.
- **Design:** The horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Job titles have been sorted by descending salary to improve readability.
- **Insights:** Quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

####  Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/0_Resources/Images/1_Salary_Dashboard_Country_Map.gif)

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design:** Colour-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country.
- **Data Organization:** Improved readability and understanding of geographic salary trends.
- **Insights:** Enabled quick grasp of global salary disparities and highlights high/low salary regions.

###  Formulas and Functions

#### Median Salary by Job Titles

```
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

- **Data Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formulas:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze arrays.
- **Insights:** Provides specific salary information for job titles, regions, and schedule types.

The purpose of the formula is to return the median salary based on job title, country, and type specified, shown in the table below.

Background Table

![1_Salary_Dashboard_Screenshot1.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot1.png)

Dashboard Implementation

<img src="/0_Resources/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Filter Function:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.

The purpose of the formula is to return a list of the unique job schedule types, shown in the table below.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](/0_Resources/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/0_Resources/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implemented the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` in the Data tab ensured:
    -  User input is restricted to predefined and validated schedule types
    -  Incorrect/inconsistent entries are prevented
    -  Overall usability of the dashboard is improved

<img src="/0_Resources/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

This dashboard was created to explore the salary trends across various data job titles based on their location and schedule types, utilizing various Excel skills such as Chart creation, Formulas and Functions and Data Validation, to ultiimately provide key insights into desired career paths.
