# Sales and Business Report with Microsoft Power BI 📊💼📈 

This repository contains the ETL (Extract, Transform, Load) process for analyzing data from the "Dunder Mifflin Paper Company.xlsx" file using Power BI. The Excel file has been pre-processed to include a "COGS" (Cost of Goods Sold) column and updated branch names from the series "The Office".

![Let's Get the Party Started](https://media.giphy.com/media/i79P9wUfnmPyo/giphy.gif)

## 1. Project description 👇
This project explores the components of Business Intelligence (BI) flow and practical uses of some DAX (Data Analysis Expressions) in Microsoft Power BI, as follows: 

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
1. Power Query Editor opens automatically after data selection.
2. Ensure the "COGS" column is present and branch names are updated.
3. Perform necessary transformations:
   - Rename columns for clarity.
   - Change data types (e.g., convert "Sale Date" to Date type).
   - Remove unnecessary columns.
   - Create calculated columns (e.g., Profit Margin: `[SalePrice] - [COGS]`).
   - Filter data as required (e.g., by date range).

![img_3](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/3.png)

![img_4](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/4.png)

### Load
1. Apply changes and close Power Query Editor.
2. Load transformed data into the Power BI data model.
3. Establish relationships between tables if multiple tables are used.
4. Create visualizations:
   - Bar charts showing sales by branch.
   - Line charts for monthly sales trends.
   - Tables displaying profit margins.

![img_5.1](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/5.1.png)

![img_5.2](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/5.2.png)

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








## DAX (Data Analysis Expressions)
This project also includes practical uses of DAX in Power BI to create calculated columns and measures for enhanced data analysis.

## Visualizations
- **Sales by Branch**: Bar chart showing sales for each branch.
- **Monthly Sales Trends**: Line chart depicting sales trends over time.
- **Profit Margins**: Table with calculated profit margins.

## How to Use
1. Download the repository and open the Power BI file.
2. Ensure the "Dunder Mifflin Paper Company.xlsx" file is in the correct location.
3. Refresh the data in Power BI to see updated analyses and visualizations.

## Requirements
- Power BI Desktop
- Excel file: "Dunder Mifflin Paper Company.xlsx"

This project explores the components of Business Intelligence flow and practical uses of some DAX (Data Analysis Expressions) in Microsoft Power BI:
**https://www.linkedin.com/feed/update/urn:li:activity:7199060482014539776?utm_source=share&utm_medium=member_desktop**

<!-- ## 1. Project description 👇

### **_Development of KPI Dashboards and Reporting System, using Power Query, Power Pivot (DAX), and NLP tools._**

For this project, I used a "Spotify App Reviews" dataset from [Kaggle](https://www.kaggle.com/datasets/mfaaris/spotify-app-reviews-2022). After being processed, the output was explored and saved in Tableau Public. -->




