# Coffee Shop Sales Analysis

### Project Overview

This project aims to analyze sales trends, customer behavior, and product performance for a coffee shop. By examining total sales, customer contributions, country-wise performance, and product popularity, the goal is to identify key revenue drivers, optimize the loyalty program, and provide data-driven recommendations to boost future business performance.

### Data Sources

Coffee Shop Data: The primary dataset used for the analysis is the "coffeeshopdata.xlsx" file containing detailed information about each sale made by the coffee shop.

### Tools

- MS Excel [Download here](http://microsoft.com)

### Data Cleaning/Preparation

In the provided Excel file, there are three sheets: **Orders**, **Customers**, and **Products**, each containing relevant data for our analysis. To make the data more useful for analysis and charting, I first created relationships between the tables based on `Customer ID` and `Product ID`.

**Imported Columns:**
1. From **Customers** sheet: `Customer Name`, `Country`, `Loyalty Card`.
2. From **Products** sheet: `Coffee Type`, `Unit Price`, `Roast Type`, `Size`, `Profit`.

**Total Sales Calculation:**
1. Created a new column, **Total Sale**, by multiplying the `Quantity` by `Unit Price`.

**Steps in Power Query:**
1. **Date Handling**: Extracted the year from `Order Date` to create a new **Year** column for analyzing sales trends.
2. **Sorting**: Sorted the `Total Sale` column from largest to smallest and rounded the data in `Unit Price` and `Total Sale` to two decimal places for consistency.
3. **Handling Missing Data**: Replaced empty cells in the `Email` and `Phone` columns in the **Customers** sheet with "Null".
4. **Postcode Format**: Changed the `Postcode` column to **Text** to accommodate both alphanumeric (Ireland and UK) and numeric (US) postcodes, avoiding errors.

### Exploratory Data Analysis

Exploratory Data Analysis (EDA) refers to the initial investigation and examination of data to discover patterns, spot anomalies, test hypotheses, and check assumptions using statistical and graphical tools. Below is a numbered list of the key EDA activities you performed in this Excel-based analysis:

#### 1. **Data Cleaning and Transformation**
   - **Addressed Missing Data**: Replaced empty cells in the `Email` and `Phone Number` columns with "Null" to ensure consistency and handle missing data properly.
   - **Standardized Postcodes**: Converted the `Postcode` column to text format to accommodate both numeric and alphanumeric entries from different countries (US, UK, Ireland).
   - **Extracted Year**: Created a new `Year` column from the `Order Date` to allow for time-based trend analysis.
   - **Rounded Numerical Data**: Rounded `Total Sales` and `Unit Price` columns to two decimal places for clarity and consistency in calculations.

#### 2. **Data Aggregation**
   - **Total Sales Calculation**: Created a new column, `Total Sale`, by multiplying `Quantity` by `Unit Price` to quantify revenue for each order.
   - **Sales and Quantity by Coffee Type**: Aggregated total sales and quantity sold for each coffee type to evaluate performance.
   - **Profit Calculation**: Analyzed the `Profit` field from the products sheet, aggregated by year to determine yearly profitability trends.

#### 3. **Top 10 Customers Analysis**
   - **Customer Segmentation**: Sorted and filtered customers based on total sales to identify the top 10 customers.
   - **Pivot Table for Customer Lifetime Value (CLV)**: Aggregated total sales by `Customer ID` to understand which customers brought the most value to the coffee shop over time.

#### 4. **Geographical Sales Analysis**
   - **Sales by Country**: Aggregated total sales based on customer country, giving a breakdown of sales distribution across regions (US, Ireland, UK).
   - **Customer Loyalty Segmentation**: Analyzed the contribution of customers with loyalty cards vs. those without, to see if loyalty programs had a significant impact on sales.

#### 5. **Product Analysis**
   - **Sales by Coffee Size**: Aggregated sales by coffee size (2.5, 1, 0.5, and 0.2 liters) to determine customer preferences for different product sizes.
   - **Coffee Type vs. Revenue**: Compared the quantity sold of each coffee type with the total revenue generated to highlight products that may be underperforming despite high sales volume.

#### 6. **Time-Based Trend Analysis**
   - **Seasonal Sales Trends**: Analyzed quarterly sales trends using the `Order Date` to spot any seasonality or high-performing periods.
   - **Yearly Profit Analysis**: Compared profits year over year to identify which years were most successful and investigate what might have driven the business performance during those periods.

#### 7. **Customer Loyalty vs Non-Loyalty Contribution**
   - **Sales Distribution by Loyalty**: Used the loyalty card data to understand the percentage of sales from loyalty customers compared to non-loyalty customers.

#### 8. **Sales and Profitability by Roast Type**
   - **Roast Type Segmentation**: Analyzed sales and profitability by `Roast Type` to determine which roast variations are most profitable and in demand (e.g., **EXC** roast type generating higher revenue).

By performing this exploratory data analysis, i was able to uncover essential insights into customer behavior, product performance, and sales trends. These analyses formed the foundation for making data-driven decisions and developing recommendations for the coffee shop's future strategies.

