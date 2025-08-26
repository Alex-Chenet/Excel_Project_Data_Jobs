# Project 2 Analysis

## Introduction

As a current job seeker i saw it fitting to show my ability to explore and show data for the most optimal jobs and skills in the data scinence job market. I set out to understand what skills top employers request and what salary would I can expect for these skills.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023-2025.
It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Do more skills get you better pay?

### Skill: Power Query (ETL)

#### Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    -  First one with all the data jobs information.
    -  The second listing the skills for each job ID.

#### Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
  - Data_Jobs_Salary

    <img width="260" height="390" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/0cf3ac54-2aef-44f3-a47c-53cb33e00f7d" />


  -  Data_Job_Skills

     <img width="261" height="429" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/f84bbb08-1f4b-4ea3-b7b8-515f509840d2" />


#### Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 Data_Jobs_Salary

        <img width="1917" height="889" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/3564d795-5e4b-4fae-9ce4-515142bfd307" />


    - 🛠️ Data_Job_Skills

        <img width="1919" height="868" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/346533c9-893c-4ac4-8649-d951832a2331" />


### Analysis

#### Insights

- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Data Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    <img width="810" height="498" alt="2_Project_Analysis_Chart1" src="https://github.com/user-attachments/assets/caddd9ad-d849-4cb8-a1ea-d5420cc9558c" />


#### So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## What’s the salary for data jobs in different regions?

### Skills: PivotTables & DAX

#### Pivot Table

- I created a PivotTable using the Data Model I created with Power Pivot.
- I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(Data_Jobs_Salary[salary_year_avg]),
        Data_Jobs_Salary[job_country] = "United States")
    ```

#### DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(Data_Jobs_Salary[salary_year_avg])
    ```

### Analysis

#### Insights

- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise. While something like Machine Larning Engineer has a large diffrence between US and non-US pay, showing the US demand for Machine Learning expertise.
- The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    <img width="743" height="680" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/142c065f-605a-481a-84f9-f2f85dfdf996" />


#### **So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## What are the top skills of data professionals?

### Skill: Power Pivot

#### Power Pivot

- I created a data model by integrating the `Data_Jobs_Salary` and `Data_Jobs_Skills` tables into one model.
- Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img width="656" height="594" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/aa00b433-b3eb-4c10-a0ba-f062422f8142" />


#### Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    <img width="1905" height="673" alt="2_Project_Analysis_Screenshot6" src="https://github.com/user-attachments/assets/5907763e-b46e-426d-bf1a-3ee73353ea3e" />

### Analysis

#### Insights

- SQL and Excel dominate as top skills in Business & Data Analyst field, reflecting their foundational role in data processing and analysis.
- Closely followed by Python the main and most known coding language in the data field. As well as Tableau and Power BI the most known and intuitive data visualization tools used by analysts. 

    <img width="1304" height="351" alt="2_Project_Analysis_Chart3" src="https://github.com/user-attachments/assets/dd023eeb-b1d1-400e-9443-8e3971392619" />


#### So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## What’s the pay of the top 10 skills?

### Skill: Advanced Charts (Pivot Chart)

#### PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - **Primary Axis:** Median Salary (as a Clustered Column)
    - **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### Analysis

#### Insights

- Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    <img width="1401" height="364" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/562413eb-5969-41d3-b0de-54249263bd4b" />


### So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As a data enthusiast and current job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and Excel. 

While my screenshots and analysis are mostly for Business and Data Analysts jobs as those are what I am currently looking for, with the power of excel and slicers this project can easly be costomized for one or more of the other jobs in my project.
