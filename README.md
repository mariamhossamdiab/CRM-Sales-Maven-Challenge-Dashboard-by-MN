# CRM-Sales-Maven-Challenge-Dashboard-by-MN 
# Introduction

Project Objective
The Quarterly Sales Performance Dashboard is designed to monitor sales performance over time, providing detailed insights into sales agents activities and outcomes across multiple quarters. The dashboard highlights opportunities won and lost, agent performance, and overall sales trends.
Goals:
1.	Improve Sales Tracking: Track the performance of sales agents across different quarters and understand their contribution to the business.
2.	Enhance Decision-Making: Provide management with data-driven insights to make strategic decisions regarding resource allocation and performance incentives.
3.	Boost Sales Efficiency: Identify the most effective sales strategies by analyzing won vs. lost opportunities, and highlighting top-performing agents.
Project Background
The project assumes the role of a Power BI developer for a company selling computer hardware to large businesses. The company has been using a new CRM system and aims to develop an interactive dashboard that sales managers can use to track the team's quarterly performance e and sales opportunities.

Objective
The main objective is to create an interactive dashboard that sales managers can use to answer the following questions:
•	How is the sales performance of the team for the given quarter?
•	How is the team performing relative to the company average?
•	What are the quarter-on-quarter sales trends of a team?
•	How is each salesperson currently performing?
•	What are the top selling products?
About The Dataset
Data set link : CRM_Sales
 
The dataset contains four tables:
•	accounts - Account details of clients including company name, industry, year established, number of employees, annual revenue, location, and parent company.
•	products - Details of products offered including product name, series, and sale price.
•	sales_pipeline - Records of sales opportunities with details including sales agent, product name, company name, sales pipeline stage, date of first engagement, date of closing a deal, and revenue.
•	sales_teams - Details of each sales agent including name, name of manager, and regional office.
# Data Cleaning 
Common Issues Detected:
  •	Missing Data
  •	Errors
  •	Duplicates
  •	Data Type Mismatches: Certain columns may have incorrect data types (e.g., times stored as text).


# Dashboard Planning
As the audience of the dashboard is sales team managers who may not be proficient with Power BI reports, the dashboard should be optimized for ease of use, requiring minimal training for its users.
The report will be split into five pages:
    •	Dashboard - This page enables team managers to quickly track overall team performance as well as the performance of each sales agent. This page will contain the following visuals:
    o	KPI cards with sub-cards that provide context to the metric values.
    o	Total sales: current, quarter-on-quarter (QoQ) growth, company average
    o	Wins (number of successful sales): current, last quarter, company average
    o	Average sale value: current, QoQ growth, company average
    o	Average days to close a deal: current, last quarter, company average.
    o	Number of engaged opportunities: number, potential sales
    •	Total sales by salesperson with company average as reference line: This enables managers to quickly assess how each sales agent performs compared to the company average.
    o	Table of sales, wins, win rates, average sales value, and average days to close for each sale agent.
    •	Sales opportunities - provides a detailed table of currently engaging opportunities. This enables managers to identify potential sales.
    •	Sales over time - This page keeps track of sales performance over time. This page will contain the following charts:
    o	Line chart of total sales and win rates by quarter.
    o	Total sales by salesperson - this can be used to cross-filter other charts on the page.
    o	Top 5 biggest wins - top 5 won opportunities with the highest sale value for the given quarter.
    •	Sales by region - This page keeps track of sales by location, industry, and product category, allowing managers to identify market trends. This page will contain the following charts:
    o	 map of sales by location
    o	Sales by industry
    o	Sales by product
    o	Win rates by product.
    o	Table of accounts with total sales and number of sales
    •	Performance by Team - This page allows managers to track their performance compared to other teams and company average. This page will contain sales, win rates, average sale value, and average days to close by manager.
# Power BI Data Modeling
•	A calendar table was created to enable time series analysis such as quarter-on-quarter growth. Table relationships were set such that all dimension tables (accounts, products, sales_teams) and the calendar table filters the sales_pipeline table through a one-to-many relationship. The calendar table uses close_date as the active relationship and engage_date as an inactive relationship. The resulting data model looks like this:
![image](https://github.com/user-attachments/assets/5fa3a2dd-a366-4621-80f4-ef72571e78d4)

 
The following measures were created to calculate key performance indicators (KPIs) for use in the dashboard:
•	Total sales, quarter-on-quarter (QoQ) sales growth, company average
•	Wins, wins last quarter, company average.
•	Win rate, win rate last quarter, company average.
•	Average sale value, QoQ growth, company average
•	Average days to close, last quarter, company average
•	Number of opportunities engaged.
•	Potential sales from engaged opportunities

The following DAX codes were used for some of the measures:
Quarter-on-quarter sales growth:



# Power BI Dashboard Building
The dashboard was built according to the dashboard plan mentioned above. Slicers for manager name, year, and quarter were added to filter the data and were also synchronized across pages.

The Dashboard page displays quarterly KPIs for the team. Clicking on a sales agent's name filters the data to show KPIs specific to the selected sales agent. Clicking column headers in the table sorts the rows by the selected metric. Lastly, clicking on the "Click to see details" button navigates to the Sales Opportunities page. 
![image](https://github.com/user-attachments/assets/5c530abf-6a24-492c-95ca-7d8fb00a1174)

The Sales Opportunities page contains details of engaged opportunities with their respective potential sale value. A slicer was created to filter the table by a sales agent.
![image](https://github.com/user-attachments/assets/84bb58b4-399b-4066-b9fd-8c37fc7f4954)

The Sales Over Time page displays sales and winr ates by quarter. Clicking a data point highlights the page by quarter. A total sales by sales agent chart can be used to filter sales over time chart by the selected agent. Finally, a table of the top 5 biggest wins can also be filtered by quarter and/or by sales agent.
![image](https://github.com/user-attachments/assets/58092354-176c-48a2-b208-9671a4757181)

 
The Sales by Region page has a choropleth map of total sales by country, total sales by industry, total sales and win rates by product, and accounts table, all of which can be used to cross-highlight visuals on the page.
![image](https://github.com/user-attachments/assets/3ea288ff-9e71-46d2-9862-16fd47fca913)

 
Finally, the performance by team has charts that visualize a manager's performance relative to other teams and with company average as reference lines.
![image](https://github.com/user-attachments/assets/050abe58-583e-4fe8-9546-56dad0814ecb)

# Conclusion
An interactive dashboard plays a key role for stakeholders to track business performance and make timely data-driven decisions. SQL can be used to profile, clean and explore the data to prepare for dashboard development.

