# Excel Salary Dashboard

![1_Salary_Dashboard_Final_Dashboard](https://github.com/user-attachments/assets/fbd16be0-6aff-4ea1-9ae9-4df57abe57ad)

## Introduction

This is a data job salary dashboard created to help visualize desired jobs for job seekers. It includes KPI cards for the desired jobs median copensation and top job platform.

### Dashboard File
My final dashboard is in [Data_Job_Salary_Dashboard.xlsx](Data_Job_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Charts**
- **Formulas and Functions**
- **Data Validation**
- **KPI Cards**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023.

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## Dashboard Build

### Charts

#### Data Science Job Salaries - Bar Chart

<img width="900" height="600" alt="1_Salary_Dashboard_Chart1" src="https://github.com/user-attachments/assets/eb40d1ce-4c18-4b65-b298-75efa1db4066" />


-  **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- **Data Organization:** Sorted job titles by descending salary for improved readability.
- **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### Country Median Salaries - Map Chart

![1_Salary_Dashboard_Country_Map](https://github.com/user-attachments/assets/4d96176a-1fb7-4cd9-ae04-af7519564b22)

- **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- **Data Representation:** Plotted median salary for each country with available data.
- **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### Formulas and Functions

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

- **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

Background Table

<img width="265" height="220" alt="1_Salary_Dashboard_Screenshot1" src="https://github.com/user-attachments/assets/9a54dfac-4e10-450e-916a-d2ceac3eb1a5" />

Dashboard Implementation

<img width="450" height="550" alt="1_Salary_Dashboard_Job_Title" src="https://github.com/user-attachments/assets/f8db9212-6993-47e1-a70d-41300c2812f9" />

#### Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

Background Table

<img width="195" height="119" alt="1_Salary_Dashboard_Screenshot2" src="https://github.com/user-attachments/assets/1d5e6331-c205-44cc-8f3e-49ad3ab48129" />

Dashboard Implementation:

<img width="350" height="500" alt="1_Salary_Dashboard_Type" src="https://github.com/user-attachments/assets/5d0e1966-6445-45a8-9601-815f67197edd" />

### Data Validation

#### Filtered List

- **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    - Incorrect or inconsistent entries are prevented
    - Overall usability of the dashboard is enhanced

![1_Salary_Dashboard_Data_Validation](https://github.com/user-attachments/assets/73d88e97-d377-4713-bc7b-2e608def799e)



## Conclusion

I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data, this dashboard allows users to make informed decisions with easily understandable key performance indicators about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 
