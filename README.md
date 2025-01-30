# HR-Analytics-using-PowerBI

## Project Overview:

This project focuses on HR analytics, leveraging a comprehensive dataset to analyze employee dynamics, satisfaction, performance, and retention patterns. Power BI, with its interactive dashboards, powerful data modeling capabilities, and DAX (Data Analysis Expressions) for calculated fields, is used to create data-driven insights. The project explores relationships between key HR metrics, such as attrition, job satisfaction, performance ratings, business travel frequency, work-life balance, and employee demographics. The objective is to help HR professionals make informed decisions to improve employee engagement, retention strategies, and workforce management.

## Objective:

The primary objective of this project is to use HR data to:

- **Analyze Employee Attrition**: Understand the factors contributing to employee attrition and retention across various demographics, departments, and job roles.
- **Evaluate Employee Engagement**: Assess job satisfaction, performance, and work-life balance to identify the drivers of employee engagement.
- **Predict Retention Risks**: Identify patterns and potential risks related to employee retention based on historical data.
- **Optimize HR Strategies**: Provide HR professionals with insights to design more effective recruitment, training, and retention strategies.
- **Provide Actionable Insights**: Generate visualizations and dashboards that HR teams can use for decision-making.

The goal is to transform raw HR data into actionable insights that drive employee retention, satisfaction, and productivity, which are essential to a company's success.

## About the Data:

The dataset consists of a range of attributes related to employees, including their demographic details, job characteristics, work environment factors, and performance indicators. The key attributes in the dataset are:

- **Attrition**: Whether an employee has left the company or is still working (Current or Ex-Employees).
- **Business Travel**: Frequency of business travel (Rarely, Frequently).
- **Age Band**: The employee’s age range (e.g., 25-34, 35-44, Over 55).
- **Department**: The department the employee works in (e.g., Sales, R&D).
- **Job Role**: Specific job position (e.g., Sales Executive, Research Scientist).
- **Job Satisfaction, Job Involvement, Work-Life Balance**: Metrics assessing employee satisfaction and engagement levels.
- **Performance Rating**: Employee performance score.
- **Marital Status, Gender, and Education**: Demographic data including marital status, gender, and education level.
- **Training Times Last Year**: Number of training sessions attended by the employee.
- **Employee Number**: Unique identifier for each employee.
- **Over Time**: Whether the employee works overtime (Yes/No).
- **Years at Company, Years in Current Role**: Tenure-related data.

This rich dataset allows for multi-dimensional analysis to uncover hidden trends, patterns, and insights across various employee attributes.

## Methodology:

- **Data Import and Preprocessing**: The dataset was imported into Power BI using **Power Query**, where the data was cleaned by handling missing values, correcting inconsistencies, and standardizing categorical variables (e.g., Gender, Marital Status).
- **ETL Process**: Using Power Query, data was transformed (filtered, pivoted, merged) to create a more efficient data model for analysis. This step ensured that data was in the proper structure for reporting.

- **DAX for Calculated Fields**: DAX (Data Analysis Expressions) was used to create custom calculated columns and measures, including:

  - **Attrition Rate**: 
    ```DAX
    Attrition Rate = DIVIDE(COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Ex")), COUNTROWS(EmployeeData), 0)
    ```

  - **Work Experience Band**:
    ```DAX
    Work Experience Band = IF(EmployeeData[YearsAtCompany] < 2, "Early Career", IF(EmployeeData[YearsAtCompany] < 5, "Mid Career", "Senior"))
    ```

  - **Employee Engagement Score** (calculated as a weighted average of satisfaction, job involvement, and work-life balance):
    ```DAX
    Engagement Score = AVERAGEX(EmployeeData, (EmployeeData[JobSatisfaction] + EmployeeData[JobInvolvement] + EmployeeData[WorkLifeBalance]) / 3)
    ```

- **Objective-Specific Visualizations**:
  - **Attrition**: Created bar charts and heat maps to visualize attrition by department, age band, and job role.
  - **Employee Engagement**: Scatter plots, box plots, and line charts were used to assess job satisfaction and work-life balance.
  - **Demographics**: Pie charts and histograms were used to visualize employee distribution by gender, education, and business travel.
  - **Training**: Line graphs and bar charts to display trends in training times, and correlate training participation with attrition and performance.

- **Dashboard Creation**: Integrated the visualizations into interactive dashboards with slicers and drill-downs, allowing HR professionals to explore data across multiple dimensions and gain deeper insights. Dashboards included filters for departments, demographics, and tenure to provide more granular insights.

## Results:

The analysis provided key insights to improve HR strategies:

- **Attrition Insights**: Higher attrition rates were observed in younger employees (aged 25-44) and in roles such as Laboratory Technicians. Low job satisfaction and work-life balance were major factors influencing attrition.
- **Business Travel & Engagement**: Frequent business travelers exhibited lower satisfaction with work-life balance, suggesting the need for better workload and travel management.
- **Employee Performance & Retention**: High performance ratings correlated with better job satisfaction and lower attrition. Employees engaged in more training programs showed lower attrition rates.
- **Demographic Trends**: Younger employees, those with shorter tenure, and those in roles with frequent overtime were more likely to leave, highlighting the need for targeted retention strategies for early-career staff.

## Actionable Recommendations:

- Implement targeted retention programs for younger employees, employees with low job satisfaction, and those with shorter tenures.
- Increase access to training programs to improve employee engagement and reduce attrition.
- Review work-life balance policies, especially for employees with frequent travel and overtime, to prevent burnout.
- Consider customized retention strategies for specific departments or roles showing higher attrition.
