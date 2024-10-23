# Coffee Shop Sales Analysis

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis and Formulas used](#data-analysis-and-formulas-used)
- [Results/Findings](#results-and-findings)
- [Recommendations](#recommendations)
- [Limitations Encountered](#limitations-encountered-during-the-analysis)
- [Dashboard Design](#interactive-dashboard-design)
- [References](#references)
---

### Project Overview

This project aims to analyze sales trends, customer behavior, and product performance for a coffee shop. By examining total sales, customer contributions, country-wise performance, and product popularity, the goal is to identify key revenue drivers, optimize the loyalty program, and provide data-driven recommendations to boost future business performance.

#### Project Dashboard

![Coffe Shop Screenshot](https://github.com/user-attachments/assets/273823ac-40b2-4d11-8ed3-dcc726478a6d)

---

### Data Sources

Coffee Shop Data: The primary dataset used for the analysis is the "coffeeshopdata.xlsx" file containing detailed information about each sale made by the coffee shop.

---

### Tools

- MS Excel [Download here](http://microsoft.com)
---

### Data Cleaning and Preparation

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
---

### Exploratory Data Analysis

Exploratory Data Analysis (EDA) refers to the initial investigation and examination of data to discover patterns, spot anomalies, test hypotheses, and check assumptions using statistical and graphical tools. Below is a numbered list of the key EDA activities you performed in this Excel-based analysis:

#### Few Important Tables 💻

- Total Sales For Each Coffee Types

|Coffee Type|Sum of Total Sale (USD)|
|-----------|-----------------------|
|Exc        |12306.39               |
|Lib        |12054.1                |
|Ara        |11768.41               |
|**Rob**        |**9005.17**               |
|Grand Total|45134.07               |


- Top 10 Customers

|Top 10 Customer Name	|Sum of Total Sale (USD)|
|-----------------------|-----------------------|
|Allis Wilmore	|317.07|
|Brenn Dundredge	|307.04
|Terri Farra	|289.11
|Nealson Cuttler	|281.68
|Don Flintiff	|278.01
|Derick Snow	|251.12
|Brice Romera	|246.21
|Alexa Sizey	|218.73
|Ailey Brash	|206.6
|Nanny Lush	|204.93
|Shelli Keynd	|204.93
|Teddi Crowthe	|204.93
|Elysee Sketch	|204.93
|Daniel Heinonen	|204.93
|Lacee Tanti	|204.93
|**Grand Total**	|**3625.15**


- Total sales by each Country

|Country	     |Sum of Total Sale (USD)|
|-------------|-----------------------|
|United States	|35638.74
Ireland	|6696.84
United |Kingdom	2798.49
**Grand Total**	|**45134.07**|


- Total Quantity ordered for each coffee type

|Coffee Type	|Sum of Quantity|
|--------------|---------------|
|Ara	|947
Rob	|878
Exc	|872
Lib	|854
**Grand Total**	|**3551**

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

---

### Data Analysis and Formulas used

The following formulas are used:

XLOOKUP
``` XLOOKUP
=[@[Product ID]],products!A:A,products!E:E)
```

TOTAL SALES
``` TOTAL
=QUANTITY*UNIT PRICE
```

TRIM
```TRIM
=TRIM(start cell:end cell)
```
---

### Results and Findings

The analysis results are as follows:
1. **Top Customer Contribution**:
   - **Wilmore** is the coffee shop’s top customer, contributing the most to overall sales. This customer alone generates a significant portion of the revenue, highlighting their importance to the business.

2. **Loyalty Program Insights**:
   - Sales from customers **without a loyalty card** make up **53%** of total sales, slightly higher than sales from loyalty cardholders, who account for **47%**.
   - The loyalty program is performing well, but there is room for improvement in encouraging more customers to join and engage with it.

3. **Popular Coffee Sizes**:
   - The **2.5-liter** size is the most popular, accounting for **53%** of sales. Other sizes lag behind: 
     - **1-liter** (24%)
     - **0.5-liter** (16%)
     - **0.2-liter** (7%)
   - Customers are heavily gravitating toward larger sizes, presenting an opportunity for further promotion of this size or boosting sales of smaller ones with targeted deals.

4. **Geographical Sales Distribution**:
   - **79%** of total sales come from **US customers**, making the US market critical for the coffee shop.
   - **Ireland** contributes **15%** of sales, while the **UK** accounts for **6%**. This suggests opportunities for growth in these regions with localized marketing efforts.

5. **Yearly Profitability Trends**:
   - **2021** was the most profitable year for the coffee shop.
   - However, **2022** has seen a drop in revenue, likely because the year’s data ends in August (the third quarter). 

6. **Coffee Type Performance**:
   - **Ara** is the best-selling coffee in terms of quantity, but **Roast Type EXC** generates more revenue despite having lower sales volume. This indicates that while **Ara** is popular, the higher-priced **EXC** roast is more profitable.

7. **Customer Segmentation Based on Loyalty**:
   - The loyalty program has helped in retaining a considerable number of customers, but additional strategies could be implemented to boost its impact, such as exclusive rewards or promotions for loyalty members.

8. **Seasonal Sales Trends**:
   - Sales fluctuate by quarter, showing some seasonality in demand. This pattern can be leveraged by planning targeted promotions during slower quarters to boost sales.

---

### Recommendations:
- **Engage High-Value Customers**: Personalized deals or loyalty incentives could retain top customers like Wilmore and increase their lifetime value.
- **Boost Loyalty Program Participation**: Further engagement with loyalty members and driving sign-ups among non-loyalty customers can increase repeat purchases.
- **Capitalize on Coffee Size Preferences**: With the 2.5-liter size dominating, promotions could focus on this size, while smaller sizes could be bundled or discounted to drive sales.
- **Expand into New Regions**: Targeted efforts in Ireland and the UK could help grow the coffee shop's presence outside the US.
- **Profit Optimization**: Promoting high-margin products like **Roast Type EXC** can boost overall profitability despite lower sales volume.

By addressing these insights, the coffee shop can optimize its sales strategy, deepen customer relationships, and improve profitability.

---

### Limitations Encountered During the Analysis

1. **Incomplete Data for Certain Fields**:
   - **Issue**: Some fields, particularly in the **Customers** sheet (e.g., `Email` and `Phone Number`), contained missing values.
   - **Impact**: This limited the ability to perform a full customer segmentation analysis or personalized marketing insights based on contact information.
   - **Solution**: Missing values were replaced with "Null" in Power Query, but ideally, the coffee shop should ensure that more complete customer data is collected at the time of purchase or registration.

2. **Postcode Format Variability**:
   - **Issue**: The `Postcode` field contained both numeric and alphanumeric formats, depending on the country (numeric for the US, alphanumeric for the UK and Ireland).
   - **Impact**: This caused inconsistency in data types, requiring manual adjustment to text format for uniformity.
   - **Solution**: Changing the data type to text addressed the issue, but it highlighted a challenge in handling global customer data where formatting standards differ. In the future, data entry validation or standardization could minimize these discrepancies.

3. **Sales Data for 2022**:
   - **Issue**: Sales data for 2022 was incomplete, only covering up until August (third quarter).
   - **Impact**: This limited the ability to make a full-year comparison and may have skewed seasonal analysis or profit trends for the year.
   - **Solution**: While insights were drawn from the available data, having full-year sales would provide a clearer understanding of the 2022 performance.

4. **Customer Segmentation by Loyalty**:
   - **Issue**: While I was able to segment customers by loyalty card status, there were no further insights available regarding customer purchasing frequency, average order value, or customer lifetime value (CLV) apart from total sales.
   - **Impact**: This limited the depth of customer behavior analysis and the ability to recommend detailed loyalty strategies.
   - **Solution**: Future analysis could benefit from more detailed customer transaction history to calculate metrics like average order value, CLV, and purchasing patterns over time.

---

### Conclusion on Limitations
While the analysis provided valuable insights into sales trends, customer behavior, and product performance, addressing the above limitations would enhance the depth and accuracy of future analyses. Data completeness, more granular time series data, and external market context could greatly benefit the coffee shop's decision-making process.

---

### Interactive Dashboard Design

To enhance the user experience, the dashboard design includes the following elements:

Font: Calibri (Body)

- Header: 36pt
- Subheaders: 18pt
- Metrics and Filters: 22pt for key figures like Total Sales, Revenue, Quantity, and Filter headings.
- Chart Text: 11pt for legibility without clutter.
- Color Scheme: Shades of coffee

- Primary Color: #513929
- Secondary Color: #DDC8B9
- Navigation Button: #644632 (text in white)
- Visuals: Rounded square shapes were used for the visuals to create a clean, modern look.

Interactive Elements: Linked navigation buttons were added to allow users to switch between sheets easily. The dashboard contains 11 visuals and 4 filters for a comprehensive view of sales, profits, and customer behavior.

---

### References
- InternPulse (Data Analysis Track)
... 







