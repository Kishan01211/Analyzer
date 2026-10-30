# PR. 2 Analyzer

A Google Sheets data analysis project that explores customer purchases,
sales performance, profit, discounts, regional performance, and
product-category trends through formulas, pivot tables, charts, and a
dashboard.

## Project Overview

**PR. 2 Analyzer** uses a sales dataset to analyze customer purchasing
behavior and business performance. The workbook includes data
preparation, conditional formatting, descriptive analysis, regression
analysis, monthly sales growth, high-value customer identification, a
pivot table, and a visual dashboard.

## Dataset Description

-   **Total records:** 200
-   **Original columns:** 9
-   **Worksheet tabs:** `Project Instructions` and `Dataset`

The original dataset contains these fields:

  Column             Description
  ------------------ ----------------------------
  Customer_ID        Unique customer identifier
  Customer_Name      Customer name
  Region             Customer/order region
  Product_Category   Product category
  Sales              Sales amount
  Quantity           Quantity purchased
  Discount           Discount rate
  Order_Date         Order date
  Profit             Profit amount

Additional analysis columns and tables were created in the `Dataset`
worksheet to complete the project requirements.

## Tools Used

-   Google Sheets
-   Spreadsheet formulas and functions
-   Pivot tables
-   Conditional formatting
-   Charts and dashboard visualizations

## Analysis and Features

### 1. Conditional Formatting

Applied conditional formatting to identify the top 10 customers based on
total purchase value.

### 2. What-If Analysis

Created discount scenarios for **0%, 5%, 10%, and 20%** to estimate the
effect of changing discounts on total profit.

The scenario formula used is:

``` excel
=SUM($I$2:$I$201)-SUMPRODUCT($E$2:$E$201,M2-$G$2:$G$201)
```

**Assumption and limitation:** The dataset does not contain a cost field
or an explicit profit recalculation rule. Therefore, this scenario is an
estimate based on the assumption that each change in discount changes
profit by the same amount per sales unit, while other factors remain
constant. It should not be interpreted as an actual forecast.

### 3. Regression Analysis

Analyzed the relationship between **Sales** and **Profit** using a
scatter chart and a linear trendline.

Google Sheets does not provide Excel's built-in Analysis ToolPak.
Spreadsheet functions were used as the equivalent numerical regression
calculations:

``` excel
=SLOPE(I2:I201,E2:E201)
=INTERCEPT(I2:I201,E2:E201)
=RSQ(I2:I201,E2:E201)
```

The workbook also includes a regression trendline chart.

### 4. Descriptive Statistics

Calculated descriptive statistics for the Sales column, including:

-   Mean
-   Median
-   Standard deviation
-   Minimum
-   Maximum
-   Count
-   Total Sales

### 5. Monthly Sales Growth

Summarized monthly sales and calculated month-over-month growth
percentages. Up and down arrows were added to indicate the direction of
sales movement.

### 6. Timestamp

Created a timestamp column using the `NOW()` function.

**Note:** `NOW()` is a volatile function. Its displayed value can update
when the spreadsheet recalculates; it is not a permanent, fixed
timestamp.

### 7. High-Value Customers

Used customer IDs, total purchase values, `INDEX`, `MATCH`, and a filter
to identify and display the top 10 high-value customers.

### 8. Pivot Table

Created a pivot table to summarize total sales by:

-   Region
-   Product Category

The pivot table also includes grand totals.

### 9. Charts and Visualizations

Created the following charts:

-   **Bar chart:** Regional sales by product category
-   **Line chart:** Product-category sales comparison across regions
-   **Pie chart:** Regional contribution to total sales
-   **Scatter chart:** Relationship between Sales and Profit, with a
    linear trendline
-   **Histogram:** Distribution of Sales values

### 10. Data Storytelling Dashboard

Created a dashboard containing key business insights and KPI values,
including:

-   Highest sales region
-   Lowest sales region
-   Best-selling product category
-   Lowest-selling product category
-   Total Sales
-   Total Profit

The dashboard combines the pivot table, summary insights, and charts to
present the analysis in a clear visual format.

## Key Project Outcomes

-   Identified high-value customers based on total purchases.
-   Compared sales performance across regions and product categories.
-   Reviewed monthly sales movement and growth.
-   Summarized sales data using descriptive statistics.
-   Examined the relationship between sales and profit.
-   Presented important findings through charts and a dashboard.

## How to Use

1.  Open the Google Sheets workbook.
2.  Select the `Dataset` worksheet.
3.  Review the original data and additional analysis columns.
4.  Review the What-If, descriptive statistics, monthly growth, and
    high-value customer tables.
5.  Explore the pivot table, charts, and dashboard.
6.  Change source data only if you intend to refresh and review the
    analysis outputs.

## Limitations

-   Google Sheets does not include Excel's Analysis ToolPak; equivalent
    spreadsheet functions were used for regression calculations.
-   The What-If profit values are assumption-based estimates because the
    source dataset does not provide cost data or a profit recalculation
    formula.
-   `NOW()` can recalculate and update; it does not create a permanent
    timestamp by itself.

## Conclusion

PR. 2 Analyzer demonstrates how Google Sheets can be used to organize
sales data, analyze customer and business performance, identify trends,
and communicate findings through pivot tables, charts, and a dashboard.
