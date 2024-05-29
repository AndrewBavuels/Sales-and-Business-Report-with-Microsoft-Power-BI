# Sales and Business Report with Microsoft Power BI 📊💼📈 

![Let's Get the Party Started](https://media.giphy.com/media/i79P9wUfnmPyo/giphy.gif)

This repository contains the ETL (Extract, Transform, Load) process for analyzing data from the "Dunder Mifflin Paper Company.xlsx" file using Power BI. The Excel file has been pre-processed to include a "COGS" (Cost of Goods Sold) column and updated branch names from the series "The Office".

Before continuing into this repository, I was already working in Power BI until reaching the point where it can be seen in the following image:

![img_0](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/0.png)

- The first thing I wanted to know was if sales were correlated with the company's profits. In the scatterplot, we can see that this is not the case. 

- We could think that the more we sell, the more profits we will have; However, we notice that there are losses in this graph.

As data professionals, we should not assume anything and take our conclusions for granted. Next, I will show you the components of my project:

## 1. Project description 👇
### _Business Analytics: EDA with Python, ETL & Power BI._

The goal is demonstrating how Python and Power BI merge together when exploring the components of Business Intelligence (BI) flow. This includes:

- Performing Exploratory Data Analysis (EDA) using Python to clean data and remove outliers in the Fact table.

- Following the EDA, the project employs ETL (Extract, Transform, Load) processes to prepare the data for advanced analysis and interactive visualizations in Power BI.

- Practical uses of DAX (Data Analysis Expressions) in Microsoft Power to create business metrics and KPIs, enabling data-driven decision-making.



### Functional architecture design:

![DM_pipeline](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/architecture/Dunder%20Mifflin%20data%20pipeline.png)

### I. Power Query for ETL
Data extraction, source consolidation, cleaning, and transformation.

### Extract
1. Open Power BI Desktop.
2. Select "Get Data" and choose "Excel".
3. Locate and select "Dunder Mifflin Paper Company.xlsx".
4. Choose the table format sheets (for this case, "Sales", "SKU" and "State_Branches").

<!-- **Example Preview**
#### Img 1 -->
![img_1](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/1.png)

#### Coming up next, we will see the dimension table "State_Branches" has no relation to the fact one "Sales"

![img_2](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/2.png)

#### So, we need to do some transforming work in Power Query:

### Transform
1. Rename columns for State_Branches by **using first rows as headers:**

![img_3](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/3.png)

2. Check the **Model View** if the relation to Sales was created:

![img_4](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/4.png)

3. Check in the **Table View** the fact table "Sales" and determine the measures we will create from:

![img_5.1](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/5.1.png)

### Load
1. Apply changes and close Power Query Editor.
2. Load transformed data into the Power BI data model.
3. Establish relationships between tables if multiple tables are used.
4. Create visualizations:
   - Bar charts showing sales by branch.
   - Line charts for monthly sales trends.
   - Tables displaying profit margins.



![img_5.2](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/5.2.png)

The ETL execution will depend on the specific needs of your data analysis. Mostly, those key moments happen when:

- Integrating new data sources.
- Updating existing data.
- Developing new analyses or reports.
- Modifying the data structure.
- Performing data maintenance or cleaning.

### II: Power Pivot (DAX) for Data Modeling
Relationships, indicators, optimization.

DAX is a formula language that allows users to create custom calculations & expressions in Power BI.

It is similar to Excel formulas but is specifically designed for use in Power BI & other Microsoft BI tools.


1. **Sales Metrics:** Compute total revenue, average order value, and sales growth. **DAX Functions:** SUM, AVERAGE, CALCULATE, YEAR-OVER-YEAR GROWTH
 
2. **Customer Behavior Analysis:** Segment customers based on purchase patterns. **DAX Functions:** COUNTROWS, FILTER, RELATED, RANKX, SWITCH
 
3. **Time Intelligence:** Analyze YTD sales, MoM growth, and YoY performance. **DAX Functions:** TOTALYTD, TOTALMTD, SAMEPERIODLASTYEAR, DATESYTD, DATEADD

- CALENDARAUTO() => DAX function for Time Intelligence
  
![img_6](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/6.png)
 
4. **Financial Reporting:** Calculate margins, ROI, and other financial metrics. **DAX Functions:** DIVIDE, CALCULATE, FILTER, ALL, RELATEDTABLE

5. **Product Performance:** Evaluate sales by category and profitability. **DAX Functions:** CALCULATE, FILTER, RELATEDTABLE, TOPN, RANKX

### III: Reporting
Data visualization, reports, dashboards, storytelling.
<!-- **Example Preview** -->

## **2. Technology stack 💻**

### Data Visualization Tools:
- [Microsoft Power BI](https://powerbi.microsoft.com/): For interactive data visualization and dashboard creation.

### Extensions and Other Tools:

- [DAX Formatter](https://www.daxformatter.com/): For formatting Data Analysis Expressions (DAX) queries.
