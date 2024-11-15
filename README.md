# Sales & Customer Performance Dashboard

![Sales   Customer Dashboard](https://github.com/user-attachments/assets/f0e99b11-0bd1-4ce0-859a-61025d5f9cf2)

# Table of Contents
* [Project Background](#project-background)
* [Data Structure](#data-structure)
* [Executive Summary](#executive-summary)
* [Recommendations](#recommendations)

# Project Background 
The objective of this project is to develop two interactive Tableau dashboards designed to empower sales managers and executives with in-depth insights into sales performance and customer behaviour. These dashboards will highlight key metrics such as monthly and weekly sales trends, product sub-category performance, and order frequency, enabling stakeholders to uncover valuable insights that can inform strategies, optimize sales, and enhance customer satisfaction across regions.

Insights and recommendations are provided on the following key areas : 
- **Total Sales, Profit & Quantity Analysis**: A comparative evaluation of historical sales trends, focusing on Total Sales, Profit, and Quantity, by analyzing both the current and previous year’s performance.

- **Sub-Category Performance Analysis**: A detailed assessment of product sub-categories, examining their contributions to sales and profits for both the current and previous year.

- **Sales & Profit Trends Over Time**: A comprehensive analysis of sales and profit trends over time, highlighting key fluctuations and patterns.

- **Customer Metrics Analysis**: An evaluation of Total Customers, Sales per Customer, and Total Orders, with a comparison of the current and previous year’s data to assess customer engagement and purchasing behavior.

- **Customer Distribution by Order Frequency**: An analysis of customer distribution based on the number of orders placed, providing insights into purchasing patterns and engagement levels.

- **Top 10 Customers by Profit**: A detailed breakdown of the top 10 most profitable customers, showcasing their contribution to overall business profitability.

Detailed Resources: 

- The Pre-Processing process utilized can be found [here](https://github.com/karlyndiary/Sales-and-Customer-Performance-Dashboard/blob/main/Pre-Processing%20%26%20Calculated%20Fields.md). 
- An interactive Tableau dashboard can be downloaded [here](https://public.tableau.com/app/profile/karen.judelyn.fernandes/viz/SalesCustomerPerformanceDashboard_17313759409300/SalesDashboard?publish=yes).

# Data Structure

Sales and Customer's database structure as seen below consists of four tables: orders, customers, location and products.

![Sales   Customer ER Diagram](https://github.com/user-attachments/assets/513a148f-4670-40a5-9415-b1328f20e47f)

# Executive Summary 

### Overview of Findings 

In November 2023, the company recorded its highest sales of the year, with 1,840 units sold, generating $118.45K in revenue and $14.45K in profit. The Phones sub-category saw significant growth, with a 33% increase in sales, while the Fasteners sub-category experienced a decline in sales. Customer metrics showed 216 customers, averaging $1,058 in sales per customer, with Raymond Buch being the top customer with $14,203 in sales. Week 49 recorded the highest weekly sales, while Week 21 saw the lowest.

Below is the overview page from the Tableau dashboard and more examples are included throughout the report. The interactive dashboard can be downloaded [here](https://public.tableau.com/app/profile/karen.judelyn.fernandes/viz/SalesCustomerPerformanceDashboard_17313759409300/SalesDashboard?publish=yes).

### Sales Dashboard
- **Monthly Sales Performance**: November 2023 was a standout month, with sales reaching their highest level of the year. The company sold 1,840 quantity, generating $118.45K in revenue and a profit of $14.45K, underscoring the month’s strong sales momentum and profitability.
- **Category Growth Analysis**: The Phones sub-category demonstrated substantial growth in 2023, achieving sales of $105.34K—a 33% increase compared to the previous year—and contributing a profit of $12.85K. In contrast, the Fasteners sub-category generated $860 in sales, reflecting an 11% decrease from the previous year, with a profit of $300.
- **Weekly Sales Trends**: Week 49 in 2023 recorded the highest weekly sales, reaching $36K, which surpassed the average weekly sales for the year. Conversely, Week 21 experienced the lowest sales at $4.36K, falling below the average.

![Sales Dashboard](https://github.com/user-attachments/assets/ab36c399-97c2-47fe-b6e6-d87bdd035f34)

### Customer Dashboard
- **Customer Metrics for November 2023**: In November, the company served a total of 216 customers, with average sales per customer reaching $1,058 and a total of 261 orders placed.
- **Order Frequency Trends**: The most common order frequencies were 1 and 2 orders per customer, with 200 customers in each category. This was followed by 156 customers with 3 orders. The least common frequencies were 7 and 8 orders per customer, with only 2 customers in each category.
- **Top Customer Profiles**: Raymond Buch led as the highest-grossing customer, with total sales of $14,203, generating a profit of $6,780 across 3 orders. Helen Wasserman ranked among the top 6 customers, contributing $8,166 in sales and $1,946 in profit from 5 orders.

![Customer Dashboard](https://github.com/user-attachments/assets/552100d3-c7e3-42f2-a2a1-693f375a9913)

# Recommendations

Based on the uncovered insights, the following recommendations have been provided : 

- **Implement a Tiered Loyalty Program**: Launch a loyalty program with multiple tiers, each offering unique benefits tailored to customer engagement levels. This could include exclusive discounts, early access to new products, and special rewards for high-value customers, fostering increased loyalty and retention.
- **Offer Seasonal Discounts on Low-Ticket Items**: Introduce seasonal "Buy One, Get One" promotions on lower-priced sub-categories. This strategy can boost sales volume for these items, attract budget-conscious customers, and encourage add-on purchases.
- **Conduct End-of-Year Customer Survey**: Deploy an end-of-year survey to gather valuable customer feedback on products, service quality, and general impressions. Insights from this survey can guide improvements, inform future product offerings, and strengthen customer relationships by showing that their opinions matter.
