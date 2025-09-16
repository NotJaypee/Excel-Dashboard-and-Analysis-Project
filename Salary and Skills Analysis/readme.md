
# Project 2 Analysis

## Introduction

As a job seeker, I noticed the limited data available on which roles and skills are most valuable in the data science field. To bridge this gap, I explored what skills employers prioritize and how they align with higher-paying opportunities.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract  

- I used **Power Query** to pull data from the source file (`data_jobs_salary_all.xlsx`) and generated two queries:  
  - 🗃️ One containing all job-related details.  
  - 🔧 Another linking each job ID to its associated skills.  


#### 🔄 Transform  

- I refined each query by adjusting column data types, removing redundant fields, standardizing text by eliminating certain words, and trimming extra spaces.  

    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/Assets/analysis_screenshot1.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/Assets/analysis_screenshot2.png)

#### 🔗 Load  

- Lastly, I imported the transformed queries back into the workbook, establishing the base for further analysis.  

    - 📊 data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/Assets/salary_table.png)

    - 🛠️ data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/Assets/skills.png)

### 📊 Analysis

#### 💡 Insights  

- 📈 Job postings that list more required skills are generally linked to higher median salaries, especially in roles such as Senior Data Engineer and Data Scientist.  
- 💼 Positions needing fewer skills, like Business Analyst, typically offer lower pay, indicating that specialized expertise drives greater market value.  


    ![2_Project_Analysis_Chart1.png](/Assets/analysis_chart1.png)

#### 🎯 Key Takeaway  

- The pattern highlights the importance of building a diverse and relevant skill set, especially for those pursuing higher-paying opportunities.  


## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table
- 🔢 Built a PivotTable from the Data Model using Power Pivot.  
- 📊 Placed `job_title_short` in the rows area and `salary_year_avg` in the values area.  
- 🧮 Added a custom measure to compute the median salary for U.S. job roles.  

    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- I used DAX to calculate the median yearly salary.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights  

- 💼 Roles such as Senior Data Engineer and Data Scientist earn higher median salaries both in the U.S. and abroad, reflecting the global demand for advanced data expertise.  
- 💰 A clear salary gap exists between U.S. and non-U.S. positions, especially in high-tech fields, likely due to the concentration of tech industries in the U.S.  

![2_Project_Analysis_Chart2.png](/Assets/analysis_chart2.png)  

#### 🔑 Key Takeaway  

- These findings provide valuable guidance for career planning and salary negotiations, enabling professionals and employers to make informed decisions while factoring in regional differences.  


## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot  

#### 💪 Building with Power Pivot  
- 🔗 Combined the `data_jobs_all` and `data_jobs_skills` tables into a single data model.  
- 🧹 Leveraged previously cleaned data from Power Query, allowing Power Pivot to automatically establish relationships.  

#### 🔗 Data Model  
- Established a relationship between the two tables through the `job_id` column.  

![2_Project_Analysis_Screenshot5.png](/Assets/analysis_chart3.png)  

### 📊 Analysis  

#### 💡 Insights  
- 💻 SQL and Python stand out as the most in-demand skills for data roles, reinforcing their importance in data management, processing, and analysis.  
- ☁️ Cloud platforms like AWS and Azure are increasingly sought after, reflecting the industry’s transition toward cloud computing and big data solutions.  

![2_Project_Analysis_Chart3.png](/Assets/analysis_chart4.png)  

#### 🔑 Key Takeaway  
- Staying current with core skills such as SQL and Python, while also developing expertise in cloud technologies, enables professionals to remain competitive and helps organizations align workforce development with market needs.  


## 4️⃣ What’s the pay of the top 10 skills?  

### 📊 Skill: Advanced Charts (Pivot Chart)  

#### 📈 PivotChart  
- Built a combo PivotChart to compare **median salary** and **skill likelihood (%)** from the PivotTable.  
  - 🪙 **Primary Axis:** Median Salary (Clustered Column)  
  - 👍 **Secondary Axis:** Skill Likelihood (Line with Markers)  
- Customized the chart by adding titles, removing connecting lines, and changing markers to diamonds for clarity.  

### 📊 Analysis  

#### 💡 Insights  
- 💰 Skills such as Python, Oracle, and SQL are linked with higher median salaries, underscoring their value in technical, high-paying roles.  
- 📉 General tools like PowerPoint and Word show the lowest salaries and likelihood, reflecting their limited demand in specialized, higher-paying positions.  

![2_Project_Analysis_Chart4.png](/Assets/analysis_chart5.png)  

### 🔑 Key Takeaway  
- Mastering high-value technical skills like Python and SQL significantly improves earning potential, making them essential investments for professionals aiming for top-paying roles in the tech industry.  


## Conclusion

As a data enthusiast and job seeker, I developed this Excel-based project to analyze trends in the data science job market. Using a dataset from real-world job postings, I explored job titles, salaries, locations, and key skills. By applying Excel tools such as Power Query, PivotTables, DAX, and advanced charting, I uncovered insights showing that roles requiring multiple technical skills—especially Python, SQL, and cloud technologies—tend to command higher salaries.  

This project reflects my ability to apply data analysis techniques to real-world scenarios and provides a resource for understanding which skills are most valuable for professionals pursuing higher-paying roles.  
