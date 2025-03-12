Shop Sphere Customer Churn Analysis

Overview

This project presents an analysis of customer churn for Shop Sphere, an e-commerce platform. The insights are derived from an extensive dataset containing customer behavioral metrics, transaction details, and demographics. The report has been generated using Power BI with DAX functions to provide valuable insights into customer tenure, order patterns, and warehouse-home distance relationships.

Dataset Description
The dataset consists of multiple customer attributes, including:
 - Customer ID
 - Churn Status (1 = Churned, 0 = Active)
 - Tenure (Duration of customer relationship)
 - Preferred Login Device (Mobile, Computer, etc.)
 - City Tier (Economic classification of the customer’s city)
 - Warehouse to Home Distance (Distance in kilometers)
 - Preferred Payment Mode (UPI, COD, Debit Card, etc.)
 - Gender
 - Hours Spent on App
 - Number of Registered Devices
 - Preferred Order Category Last Month
 - Satisfaction Score
 - Marital Status
 - Number of Addresses
 - Complaints in Last Month
 - Order Amount Hike from Last Year
 - Coupons Used in Last Month
 - Order Count in Last Month
 - Days Since Last Order
 - Cashback Amount Received in Last Month

Key Analytical Approaches

1. Customer Tenure Classification
To assess customer longevity, tenure is categorized using the following **DAX functions**:

```DAX
Minimum Tenure Customer = MIN('E Comm'[Tenure])
Median Tenure Customer = MEDIAN('E Comm'[Tenure])
Maximum Tenure Customer = MAX('E Comm'[Tenure])

Tenure Customer Range = 
IF('E Comm'[Minimum Tenure Customer] <= 10, "Bronze",
   IF('E Comm'[Median Tenure Customer] <= 20, "Silver","Gold"))
```
This classification helps in segmenting customers into Bronze (short-term), Silver (medium-term), and Gold (long-term).

2. Warehouse to Home Distance and Order Patterns
To understand the impact of distance on ordering behavior, the following calculations are used:

```DAX
Minimum distance from warehouse to home = MIN('E Comm'[Warehouse To Home])
Median Warehouse to Home = MEDIAN('E Comm'[Warehouse To Home])
Maximum distance from warehouse to home = MAX('E Comm'[Warehouse To Home])

Customer to warehouse Distance = 
IF('E Comm'[Minimum distance from warehouse to home] <= 20, "Near",
   IF('E Comm'[Median Distance from Warehouse to Home] <= 30, "Medium","Far"))
```
This segmentation helps evaluate the correlation between distance and order frequency.

3. Device Usage Insights
The average number of devices registered per customer is calculated using:

```DAX
Average number of devices registered = AVERAGE('E Comm'[Number Of Device Registered])
```
This metric is useful in understanding multi-device engagement trends among customers.

Key Findings from the Report
 - Total Cashback Issued (Last Month): $619.74K
 - Total Complaints Registered: 1,065
 - Preferred Payment Mode Distribution: 
  - UPI: 7.55%
  - COD: 9%
  - Credit/Debit Cards & Wallets: Major chunk (40.75%)
 - Churn vs. Orders Analysis:
  - Higher churn rates among short-tenured customers (Bronze segment)
  - Customers closer to warehouses tend to order more frequently
 - Most Popular Order Categories (Last Month):
  - Fashion
  - Laptops & Accessories
- Average Hours Spent on App by Active Users: Varies by tenure

Conclusion

This report provides **critical insights into customer churn and purchasing behavior**, enabling **Shop Sphere** to improve retention strategies. The analysis highlights factors affecting churn, such as tenure, warehouse-home distance, and device usage.
