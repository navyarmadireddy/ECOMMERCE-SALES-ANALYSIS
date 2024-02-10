# ECOMMERCE-SALES-ANALYSIS
This repository contains an E-commerce Analytics dashboard designed to analyze and visualize sales and profitability data within an online retail company. The dashboard gives insights into sales performance, customer behavior, and factors influencing profitability, providing valuable information for optimizing business strategies.

## Problem Statement:
 
E-Commerce refers to the buying and selling of goods or services over the internet. As online shopping becomes increasingly prevalent, businesses face the challenge due to the vast amounts of data generated from online transactions and encounter difficulties in comprehensively understanding their sales data and maximizing their competitiveness in the digital marketplace. 


#### Objective: 
To analyze E-Commerce sales data to uncover insights into sales patterns, customer behaviors, and market trends that will drive strategic decisions and improve business performance.

#### Questions: 
Questions are important to get the objective of our analysis and to generate insights.

[1] Which states among Top 10, which categories contribute the most to overall profit?

[2] What are the top-5 best selling sub categories?

[3] Are there specific months with significant sales spikes?

[4] What is the most common shipping mode used?

[5] What is the difference in sales before and after discount.




### Steps followed 

- Step 1 : IMPORT THE DATA SET 
    
    Import the data set in Excel and understand each attribute.
        
    - Row Id – unique row id for each row 
    - Order id – unique order id for each customer
    - Order date – order date of the product 
    - Ship date – shipping date of the product
    - Ship mode – shipping mode specified by the customer 
    - Customer id – unique id to identify each customer 
    - Customer Name – name of the customer
    - Segment – segment where the customer belongs
    - Country – Country details
    - State - State details
    - City - City details
    - Postal Code - Postal Code details
    - Region - Region details
    - Product id – unique id for each product 
    - Category – category to which the product belongs
    - Sub category - sub category to which the product belongs 
    - Product name – name of the product
    - Sales – sales of the product sold 
    - Quantity – no of items of the product ordered by that customer
    - Discount – any discount given 
    - Profit – profit or loss incurred

- Step 2 : DATA CLEANING
  - Handling missing values 
    - Identify columns with missing values and decide appropriate strategy to handle missing data – remove rows, impute values or use a default value.
    - To check missing values (null) create drop down for table columns using short cut Alt+D+F+F. Now from the drop down list check if any null values are there.
    - Or Select all data > Ctrl + G > Special > Blanks gives if any cells are blank
    - No missing values (null values) are found in our data set.
  - Remove Duplicate data record or redundant column
    - Check for duplicate record and remove them if necessary, ensure that it won’t effect the analysis.
    - Select all data > Click the Data tab > select Remove duplicates icon under Data tools.
    - No duplicate record are found in our data set.
  - Data type conversion
    - Ensure that each column has correct data type.  
    - Convert to required data type if necessary.
    - Changed Order date, Ship date to date format. Changed Sales, Quantity, Profit to Number Profit. Changed Discount to percentage.
  - Standardizing text data
    - Standardize text data to ensure consistency (eg. Capitalization, leading/trailing spaces)
    - Our data is in Standardized format only.
  - Handling Inconsistent data
    - Look for variations in categorical data and standardize them to consistent form.
    - Use Find and Replace to replace the inconsistent data.
    - There is no inconsistent data in our data set.

- Step 3 : ADDITIONAL COLUMNS 
    
    Create any Additional columns required for creating pivot tables.
    - New columns for year and month are created.
        =TEXT("order date","yyyy") and =TEXT("order date,"mmmm")
    - New column is created to differentiate if the item has discount as “Zero Discount”, “With Discount”.Using Conditional formula =IF(T2=0,”Zero Discount”,”With Discount”). This is useful for sales analysis with discount.

- Step 5 : PIVOT TABLES 

    Create Pivot tables to design Visualizations.

    [1]	Which are the states that contribute the most to overall profit among top 10?
    - PivotTable is created with the "State" field in the Rows area and the "Profit" field in the Values area to analyze profit contributions by state.
    - Sorted the values using the Sort & Filter feature in the Home tab, then filtered the top 10 states with the highest profits by selecting "Value Filters" > "Top 10" from the Column dropdown menu
    - Generated a Bar Chart based on the PivotTable data to visually represent the profit contributions of each state, from which we observe that New York and California are the top contributors.

    [1.2]	Which categories contribute the most to overall profit?
    - PivotTable is created with the "Category" field in the Rows area and the "Profit" field in the Values area to display total profits by category.
    - Donut Chart is generated based on the PivotTable data to visually represent the contribution of each category to overall profit
    - From the Chart it's evident that Office Supplies and Technology emerge as the top contributors.

    [2] What are the top-5 best selling sub categories?
    - Pivot Table is created with “Sub Category” column in Rows area and “Sales” column in Values area to display total sales by sub category.
    - Click on any cell within the “Sales” column, In the Sort & Filter “Sort Largest to Smallest”, this sorts the sales in descending.
    - Dropdown from column label > Value filter> Top 10> change to 5 to get top5 products.
    - Generated a Pie Chart to visually represent this.

    [3] Are there specific months with significant sales spikes?
    - PivotTable is created with "Order Date" in the Rows area and "Sales" in the Values area to display total sales by month.
    - From Line Chart generated we can observe a significant sales spikes in the months September and November.

    [4]	What is the most common shipping mode used?
    - Pivot Table created with “Ship Mode” in Rows area and “Customer Id” in Values area to display count of customer Id for each ship mode which helps us to know the prefrred shipping mode by customer.
    - Generated a Column Chart from where we can observe that the Ship Mode “Standard Class” is most commonly used.

    [5] What is the difference in sales before and after discount.
    - Pivot Table created with "Sub Category" in Rows area and "Sales" in Values area and "Discount Status" in Column area to understand the sum of sales of each subcategory with respect to discount.
    -  The difference in sales before and after discount varies across different sub-categories. Some sub-categories show an increase in sales after discounts, while others show a decrease.

- Step 6: KPI and Slicers
    - Pivot table is created with Sales, Profit, Quantity in Values area, Month in Rows area, Year in Filter area to get the key performance indicates total sales, total profit, total quantity sold.
    - Slicers are created for Year, Region, Segment and connection is made to all pivot tables.



# Snapshot of Dashboard 

![Ecommerce_Sales_Dashboard](https://github.com/navyarmadireddy/ECOMMERCE-SALES-ANALYSIS/assets/122340189/93fc2aea-7d41-4ea2-afda-c091a249fc70)



# Insights

Following inferences can be drawn from the dashboard;

### [1] Top Contributing States:

-  New York and California are the top contributing states to overall profit. 
- Actions: Implement targeted marketing campaigns in these states to capitalize on existing customer bases and increase market share. 

### [2] Key Profitable Categories:

- Office Supplies and Technology emerge as the top contributors to overall profit. 
- Actions: Invest in expanding product offerings within these categories, introduce new product lines or variations to cater to evolving customer needs.  Prioritize marketing efforts and promotions for these categories to drive sales and maximize profitability.
           
### [3] Best Selling Sub-Categories:

- Top 5 best-selling sub-categories changes region wise.
- Actions: Optimize inventory management for these high-demand products to ensure availability and minimize stockouts in those regions. 
  
### [4] Sales Spikes in Specific Months:

- Significant sales spikes are observed in September and November. 
- Actions: Leverage seasonal trends and consumer behavior insights to plan targeted promotions or sales events during these months. Offer special discounts or incentives to capitalize on increased consumer spending and drive higher sales volumes.

### [5] Preferred Shipping Mode:

- Standard Class shipping mode is identified as the most commonly used. 
- Actions: Evaluate shipping logistics and delivery timelines to ensure efficient and reliable service for customers choosing Standard Class shipping. 

### [6] Impact of Discounts on Sales:

- Sub-categories that show a significant increase in sales after discounts indicate that customers are price sensitive and more responsive to discounts in those product categories.
- Actions: Consider implementing targeted discount promotions or adjusting pricing strategies to capitalize on customer preferences and drive sales.

The analysis offers valuable insights into e-commerce performance and profitability. To address challenges and capitalize on opportunities, the organization should prioritize initiatives such as optimizing marketing efforts in top contributing states, expanding product offerings in profitable categories, refining discounting strategies based on customer responsiveness, leveraging seasonal sales spikes for targeted promotions, and enhancing shipping logistics to meet customer preferences. These initiatives will enable the organization to drive sales, improve customer satisfaction, and achieve sustainable growth in the competitive e-commerce market.

