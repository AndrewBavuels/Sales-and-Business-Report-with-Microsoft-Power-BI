# Sales and Business Report with Microsoft Power BI 📊💼📈 

![Let's Get the Party Started](https://media.giphy.com/media/i79P9wUfnmPyo/giphy.gif)

This repository contains the ETL (Extract, Transform, Load) process for analyzing data from "Dunder Mifflin Paper Company" **sales.xlsx file** using Power BI. The Excel file has been pre-processed to include a "COGS" (Cost of Goods Sold) column and updated branch names from the series "The Office".

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

### I. Exploratory Data Analysis (EDA)

Here is a little extract from Jupyter Notebook, using Python and their libraries (described down in the Technology Stack section).

![EDA_with_Python](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/EDA%20with%20Python.png)

Remember when I first detected the **outliers** in the Power Bi Visualization? Well, this is the part and I am performing their handling per each **customer segment**

### II. Power Query for ETL
Data extraction, source consolidation, cleaning, and transformation.

### Extract
1. Open Power BI Desktop.
2. Select "Get Data" and choose "Excel".
3. Locate and select "sales.xlsx".
4. Choose the table format sheets (for this case, "FACT_Sales", "DIM_SKU" and "DIM State_Branches").

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
4. Create Measures for the columns previously marked in the red rectangle:
   - Quantity.
   - Sales.
   - COGS.
   - Profit.



![img_5.2](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/5.2.png)

The ETL execution will depend on the specific needs of your data analysis. Mostly, those key moments happen when:

- Integrating new data sources.
- Updating existing data.
- Developing new analyses or reports.
- Modifying the data structure.
- Performing data maintenance or cleaning.

### III: Power Pivot (DAX) for Data Modeling
Relationships, indicators, optimization.

DAX is a formula language that allows users to create custom calculations & expressions in Power BI.

It is similar to Excel formulas but is specifically designed for use in Power BI & other Microsoft BI tools. **Some of them used were:**


1. **Sales Measures:**
     - Total Sales = SUM ( FACT_Sales[Sales] )

     - Sales Ranking = RANKX ( ALL ( 'DIM state_branches'[Branch] ), [Total Sales] )

     - Cumulative Total Sales = CALCULATE ( [Total Sales],  TOPN ( [Sales Ranking], ALL ( 'DIM state_branches'[Branch] ), [Total Sales] ))

     - % Sales Performance = [Cumulative Total Sales]    / CALCULATE ( [Total Sales], ALL ( 'DIM state_branches'[Branch] ) )

2. **Time Intelligence:**
    - DIM_Calendar = CALENDARAUTO() 
  
![img_6](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/6.png)
 
4. **Financial Reporting:** Calculate margins, ROI, and other financial metrics. **DAX Functions:** DIVIDE, CALCULATE, FILTER, ALL, RELATEDTABLE

5. **Product Performance:** Evaluate sales by category and profitability. **DAX Functions:** CALCULATE, FILTER, RELATEDTABLE, TOPN, RANKX

### IV: Reporting
Data visualization, reports, dashboards, storytelling.

### The 5 Whys

1. **Why are sales and profit not correlated?**
   Because more sales do not necessarily mean more profit.

2. **Why do more sales not necessarily mean more profit?**
   Because some sales result in losses.

3. **Why do some sales result in losses?**
   Because their costs are higher than the revenue generated from those sales.

4. **Why are their costs higher than the revenue?**
   Because in some branches, operational costs are higher.

5. **Why are their operational costs higher?**
   Maybe it has to do with some products that are complex to sell.



## **2. Technology stack 💻**

### Data Visualization Tools:
- [Microsoft Power BI](https://powerbi.microsoft.com/): For interactive data visualization and dashboard creation.

### Extensions and Other Tools:

- [DAX Formatter](https://www.daxformatter.com/): For formatting Data Analysis Expressions (DAX) queries.

![DAX_Formatter](https://github.com/AndrewBavuels/Sales-and-Business-Report-with-Microsoft-Power-BI/blob/main/images/DAX%20Formatter.png)
