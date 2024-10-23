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
- From **Customers** sheet: `Customer Name`, `Country`, `Loyalty Card`.
- From **Products** sheet: `Coffee Type`, `Unit Price`, `Roast Type`, `Size`, `Profit`.

**Total Sales Calculation:**
- Created a new column, **Total Sale**, by multiplying the `Quantity` by `Unit Price`.

**Steps in Power Query:**
1. **Date Handling**: Extracted the year from `Order Date` to create a new **Year** column for analyzing sales trends.
2. **Sorting**: Sorted the `Total Sale` column from largest to smallest and rounded the data in `Unit Price` and `Total Sale` to two decimal places for consistency.
3. **Handling Missing Data**: Replaced empty cells in the `Email` and `Phone` columns in the **Customers** sheet with "Null".
4. **Postcode Format**: Changed the `Postcode` column to **Text** to accommodate both alphanumeric (Ireland and UK) and numeric (US) postcodes, avoiding errors.


