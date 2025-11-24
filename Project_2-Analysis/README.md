
# Project 2 Analysis

## Introduction

This project was performed to explore the most optimal roles and skills in the data job market. I set out to understand which skills top employers request, and how to secure a higher pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills

The following skills were utilized for analysis:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. 

It includes information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## 1️. Do more skills get you better pay?

#### Power Query (ETL): Extract

- I used Power Query to extract the original data (`data_salary_all.xlsx`) and created two queries:
    -  1: Contained all of the data jobs information.
    -  2: Listed the skills for each job ID.

#### Transformation:

- I transformed each query by adjusting columns and cleaning text to eliminate specific words, and trimming excess whitespace.
    -  data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/0_Resources/Images/2_Project_Analysis_Screenshot1.png)

    -  data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/0_Resources/Images/2_Project_Analysis_Screenshot2.png)

####  Load:

- I loaded both transformed queries into the workbook, ready for subsequent analyses.
    -  data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/0_Resources/Images/2_Project_Analysis_Screenshot3.png)

    -  data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/0_Resources/Images/2_Project_Analysis_Screenshot4.png)

####  Insights:

-  There is a positive correlation between the number of skills in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Analyst.
-  Roles that require fewer skills, such as Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/0_Resources/Images/2_Project_Analysis_Chart1.png)

#### Conclusion-1:

- The results highlight the importance of building on a broad set of relevant skills, which are required to achieve higher-paying roles.

## 2️. What’s the salary for data jobs in different regions?

#### Pivot Table:

-  A PivotTable was created using the data model from Power Pivot.
- `job_title_short` was moved to the rows area and `salary_year_avg` into the values area.
-  The median salary was measured for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### DAX:

- The median yearly salary was calculated using the following formula:

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

####  Insights:

-  Roles such as Senior Data Engineer and Data Engineer offer higher median salaries both in the US and globally, showcasing the global demand for advanced data expertise.
-  The salary disparity between US and Non-US positions are pronounced in high-tech jobs, which may be influenced by the strong concentration of tech industries within the US.

    ![2_Project_Analysis_Chart2.png](/0_Resources/Images/2_Project_Analysis_Chart2.png)

#### Conclusion-2:

- These findings help guide compensation planning and negotiations, highlightiing market norms and regional pay variations.

## 3. What are the top skills of data professionals?

####  Power Pivot:

- A data model was created by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- A relationship was created between the two tables, specifically the `job_id` column, shown below.

#### Data Model:

  ![2_Project_Analysis_Screenshot5.png](/0_Resources/Images/2_Project_Analysis_Screenshot5.png)

#### Insights:

- The results show that SQL and Python dominate as the top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- A notable demand for AWS and Azure show a broader industry, which may reflect a transition towards cloud-based infrastructures.

    ![2_Project_Analysis_Chart3.png](/0_Resources/Images/2_Project_Analysis_Chart3.png)

#### Conclusion-3:

- Understanding which skills dominate the data industry keeps professionals competitive and helps training programs prioritize the most valuable skills/technologies.

## 4️. What’s the pay of the top 10 skills?

#### PivotChart:

- A combo PivotChart was created to plot median salary and skill likelihood (%) of my Pivot Table.
    -  **Primary Axis:** Median Salary (as Columns)
    -  **Secondary Axis:** Skill Likelihood (as Markers)
 
![2_Project_Analysis_Chart4.png](/0_Resources/Images/2_Project_Analysis_Chart4.png)

#### Insights:

-  Skills such as Python, Oracle and SQL align with higher median salaries, highlighting their value in top-paying positions.
-  Skills such as PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

### Conclusion-4:

- The data emphasizes that high-value skills - particularly Python and SQL - correlate to higher compensation, reinforcing their importance in the data job market.

## Final points

These insights illustrate a rapidly evolving tech marketplace where advanced, cloud-driven, and data-centric skills may be commanding the greatest value. As organizations continue investing in digital transformation, the demand for highly skilled data professionals will only deepen. Individuals building expertise in these areas have a greater chance to be best positioned to thrive in the demands of the tech industry.
