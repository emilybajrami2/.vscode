# Introduction
This project explores the top-paying and most in-demand skills for Data Analyst roles in the United Kingdom based on 2023 job posting data. The goal is to identify which skills offer the best combination of job security (high demand) and financial reward (high salary). The analysis provides insights for aspiring and current data analysts on which technical skills are most valuable to develop.

SQL Queries: [project_sql folder](/project_sql/)

# Background
As the data industry continues to expand, employers are seeking analysts who can bridge data manipulation, visualisation, and cloud technology. This analysis uses job posting data to evaluate trends in required skills, average salaries, and demand levels across the UK market.
### The questions I wanted to answer through my SQL queries were:
1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for data analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

# Tools I Used
- **SQL:** The backbone of my analysis, allowing me to query the database and unearth critical insights.
- **PostgreSQL:** The chosen database management system, ideal for handling the job posting data.
- **Visual Studio Code:** My go-to for database management and executing SQL queries.
- **Git & GitHub:** Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project tracking.
# The Analysis
### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered data analyst positions by average yearly salary and location, focusing on UK jobs. This query highlights the high paying opportunities in the field.

```sql
SELECT
    job_id,
    name AS comany_name,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date:: DATE
FROM 
    job_postings_fact
LEFT JOIN company_dim
    ON job_postings_fact.company_id = company_dim.company_id
WHERE
    job_title_short = 'Data Analyst' AND
    job_location = 'United Kingdom' AND
    salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10;
```
- **Wide Salary Range:** Top 10 UK Data Analyst roles in 2023 show a significant salary spread, with average annual pay ranging from £60,000 to over £150,000. This highlights the strong earning potential for analysts with advanced technical skills such as Python, SQL, and cloud-based tools. Higher salaries are typically linked to roles requiring data engineering, automation, or business intelligence expertise, reflecting how skill specialisation drives financial reward in the UK job market.

- **Core Skill Range:** The top 10 data analyst positions most commonly required Python, Excel, SQL, and Tableau, highlighting the balance between coding, data manipulation, and visual storytelling. These skills represent the foundation of modern data analysis workflows.

![Top Paying Roles](assets\average_salary_distribution.png)

*Bar graph visualizing the salary for the top 10 salaries for data analysts; ChatGPT generated this graph from my SQL query results*

# What I Learned

# Conclusions

This project enhanced my SQL skills and provided valuable insights into the data analyst job market. The findings from the analysis serve as a guide to prioritizing skill development and job search efforts. Aspiring data analysts can better position themselves in a competitive job market by focusing on high-demand, high-salary skills. This exploration highlights the importance of continuous learning and adaptation to emerging trends in the field of data analytics
