
# Employee Churn Analysis and Retention Prediction

This project involves the development of an employee churn prediction model, coupled with a dashboard for visualizing insights and supporting HR strategies. Using data science techniques and machine learning, the project identifies at-risk employees and provides actionable insights to enhance employee retention.

##  Project Overview

- Goal: 
    - Predict employee churn (i.e., likelihood of leaving the company).

    - Identify factors influencing churn.

    - Provide actionable insights for retention strategies.

- Key Tools and Technologies:

    - Python: For data analysis and machine learning.

    - Pandas: Data manipulation and preprocessing.

    - PyCaret: Model building and evaluation.

    - Google BigQuery: Data storage and retrieval.

    - Google Looker Studio: Dashboard creation for visualization.

- Machine Learning Model:

    - Algorithm: Random Forest Classifier.

    - Performance:

        - Accuracy: 92%

        - AUC-ROC: 0.90

## Dataset

- Dataset Sizes:

    - First Dataset is of HR data with 15,000 employees
    - Second Dataset is of new employees with 100 entries


- This indicates:

    - HR Data represents historical employee data and new employee data likely represents recent new hires or incoming employees.

    - The ratio is 150:1; so Second dataset is about 0.67% the size of the original dataset.



- This difference in size affects how we should approach our analysis:

    - For comparative analysis:

        - We'll need to be careful about drawing conclusions from second dataset due to smaller sample size and hence Percentages and proportions will be more meaningful than absolute numbers.


    - For machine learning or predictive modeling:

        - First dataset would be more suitable for training due to larger sample size and second dataset could be used as a validation set or for making predictions about new employees.

- Employment Status:

    - First dataset showed employees who had quit (Quit_the_Company = 1)
    - Second dataset shows current employee (Quit_the_Company = 0)


- Department Distribution:

    - More diverse department representation including:

        - Technical
        - Accounting
        - R&D
        - Sales
        - Support
        - IT
        - HR
        - Product Management
        - Marketing
        - Management

    - Salary Distribution:

        - More varied salary levels (low, medium, high)
        - First dataset was predominantly "low" salary

- The dataset includes employee information such as:

    - Satisfaction Level

    - Last Evaluation Score

    - Number of Projects

    - Average Monthly Hours

    - Tenure at the Company

    - Department

    - Salary Level

    - Work Accidents

## Features and Insights

   - Feature Importance:

        - The model identified Job Satisfaction as the most critical factor (30% impact).

        - Other key factors: Time spend in the company, Number of Projects taken, and Last Evaluation.

   - Department-Specific Trends:

        - High Churn Departments:

            Sales and Technical.

        - Low Churn Departments:

            R&D and Accounting.

   - Churn Drivers:

        - Low satisfaction
        - high workload
        - lack of growth opportunities 
        - Surprisingly, work accidents had minimal impact.

## Workflow

   - Data Loading:

        - Retrieved datasets from Google BigQuery into Pandas DataFrames for preprocessing.

   - Data Preprocessing:

        - Handled missing values, encoded categorical features, and normalized numeric features.

   - Model Development:

        - Used PyCaret for model comparison and training.

        - Selected Random Forest Classifier for its robust performance and feature importance analysis.

   - Predictions:

        - Applied the model to predict churn on current and new employee datasets.

   - Visualization:

        - Built an interactive dashboard in Google Looker Studio:

            - Visualized churn by department.

            - Highlighted feature importance and employee sentiment.

## Dashboard

This is the link for the looker studio dashboard: 
https://lookerstudio.google.com/s/srXMJfNxnpwhttps://lookerstudio.google.com/s/srXMJfNxnpw

- Key Metrics at the Top:

    - 7.0% appears to be the overall churn rate

    - 10 different departments are being analyzed

    - Average satisfaction level is 0.5

    - Average last evaluation score is 0.5

    - Average tenure (Total Years) is 3.4 years

- The dashboard aims to identify at-risk employees and uncover factors contributing to employee turnover. Its key goals are:

    - Identifying At-Risk Employees: Using predictive models to flag employees likely to leave.

    - Understanding Turnover Causes: Analyzing factors influencing churn, like job satisfaction, workload, and career growth opportunities.

    - Enhancing Retention Strategies: Developing targeted retention programs based on insights from the churn model.

- Supporting Metrics: The dashboard showcases several important metrics:

    - Satisfaction Level: A primary indicator of whether employees are likely to stay or leave.

    - Total Years: Represents the average tenure of employees.

    - Other Metrics: Average values for factors like: 

        - Last Evaluation: Performance evaluations.

        - Time Spent at the Company.

        - Number of Projects.

        - Average Monthly Hours.

        - Work Accident: A less impactful factor.

- Key Insights from the Random Forest Algorithm:

    - Most Crucial Factors:

        - Job Satisfaction: The most critical factor influencing employee decisions.

        - Project Involvement: A moderate number of projects positively correlates with retention.

        - Workload and Evaluations: Moderate working hours and higher performance evaluations also encourage retention.

- Visualizations

    - The horizontal bar chart shows the most important factors affecting employee churn:

        - satisfaction_level is the most influential factor (around 30-35%)

        - time_spend_company

        - number_project

        - average_monthly_hours

        - last_evaluation

        - Work_accident

        - salary_low (having lowest impact among shown factors)

    ![Not found](https://github.com/Pret-Hub/Data-Analysis-Project/blob/main/What%20is%20causing%20churn.png)

    - Displays sentiment predictions for employees, segmented into:
        - Predicted to Stay.
        - Predicted to Quit.

    - Highlights which departments have the highest employee turnover. Examples:

        - Departments with High Churn: Sales, technical.

        - Departments with Low Churn: Research and Development (R&D), accounting.

    ![Not found](https://github.com/Pret-Hub/Data-Analysis-Project/blob/0ab7ba4ff55ebe5e12f8ee0b7b376f923496ad91/From%20where%20people%20are%20leaving.png)

## Key Metrics

   - Model Performance:

        - Accuracy: 92%

        - AUC-ROC: 0.90

   - Dashboard Highlights:

        - 40% improvement in reporting efficiency through automation.

        - Clear visualization of churn trends and department-specific risks.

## Recommendations

   Employee Recognition program
        - Acknowledging and rewarding employees boosts job satisfaction and motivation, addressing a key factor in reducing turnover.

   Professional Development Initiatives:
        - Investing in training and development helps employees grow within the company, increasing their commitment and job satisfaction.

   Reward long term Employees:
        - Offering retention incentives encourages long-term commitment, addressing the importance of time spent with the company.

## Future Enhancements

   - Expand Dataset:

        - Incorporate external data sources such as industry benchmarks, employee feedback surveys, and market salary data to enhance model robustness and accuracy.

        - Increase the size and diversity of the dataset to ensure generalizability across different business contexts.

   - Advanced Analytics:

        - Implement advanced feature engineering techniques, such as interaction terms between variables, time-based trends, and rolling averages, to improve model interpretability and predictions.

        - Explore clustering algorithms (e.g., K-Means) to group employees based on behavior or churn risk.

   - Enhanced Visualization:

        - Add more granular insights in the dashboard, such as individual employee risk scores or department-specific breakdowns.

        - Introduce trend analysis visualizations to monitor changes in churn rates and satisfaction over time.

   - Custom Alerts:

        - Build a notification system in the dashboard to alert HR teams about high-risk employees or departments based on real-time data changes.

        - Include thresholds for automatic warnings when churn indicators exceed predefined levels.

   - Integration with HR Systems:

        - Integrate the churn model and dashboard with existing HR tools (e.g., SAP SuccessFactors, Workday) to provide seamless access to predictions and insights.

        - Enable real-time data synchronization to reflect the latest employee metrics in the dashboard.




## 🔗 Links
[This is my Dashboard Link](https://lookerstudio.google.com/s/srXMJfNxnpw)

[Collab Notebook Link](https://github.com/Pret-Hub/Data-Analysis-Project/blob/main/Employee_analysis.ipynb)

 
