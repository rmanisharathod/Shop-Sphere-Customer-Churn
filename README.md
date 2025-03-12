Shop Sphere - Customer Churn Dataset


Overview

This dataset contains information about customer behavior and churn in an e-commerce platform, "Shop Sphere." The dataset includes key attributes such as tenure, login preferences, payment methods, customer demographics, complaints, and order-related data. The goal is to analyze factors influencing customer churn and gain insights into customer retention strategies.

Dataset Description

The dataset consists of multiple attributes that provide insights into customer activity, purchasing patterns, and satisfaction levels.


Columns Description

- CustomerID: Unique identifier for each customer.
- Churn: Indicates if the customer has churned (1) or is still active (0).
- Tenure: Number of months the customer has been with the platform.
- Preferred Login Device: The device most frequently used by the customer to access the platform (e.g., Mobile Phone, Computer).
- City Tier: Indicates the classification of the customer's city based on economic and infrastructural development.
- Warehouse To Home: Distance between the nearest warehouse and the customer's address.
- Preferred Payment Mode: The most commonly used payment method by the customer (e.g., Debit Card, Credit Card, UPI, E-Wallet, COD).
- Gender: Gender of the customer (Male/Female).
- Hour Spend On App: Number of hours the customer spends on the e-commerce app per month.
- Number Of Device Registered: Number of devices linked to the customer's account.
- Preferred Order Category in Last Month: The product category that the customer purchased the most in the last month (e.g., Fashion, Laptop & Accessories, Others).
- Satisfaction Score: A score representing the customer's satisfaction level.
- Marital Status: Marital status of the customer (Single, Married, Divorced).
- Number Of Addresses: Total number of addresses registered by the customer.
- Complain in Last Month: Number of complaints raised by the customer in the past month.
- Order Amount Hike From Last Year: Percentage increase in the customer's total order value compared to last year.
- Coupon Used in Last Month: Number of coupons applied by the customer in the last month.
- Order Count in Last Month: Total number of orders placed by the customer in the last month.
- Day Since Last Order: Number of days since the customer last placed an order.
- Cashback Amount in Last Month: The cashback earned by the customer in the last month (in USD).


Insights from Report

- The dataset is supported by an analytical report that provides the following key findings:
- The total cashback amount given in the last month was approximately $619.74K.
- 1065 customer complaints were registered.
- The most preferred login device is Mobile Phone.
- The most common preferred payment mode includes Debit Card, Credit Card, and UPI.
- A total order amount hike of $59K was observed compared to the previous year.
- The Laptop & Accessory category had significant customer engagement.
- Customer complaints and satisfaction scores can provide critical insights into churn prediction.

It includes key insights derived from customer tenurity, warehouse-to-home distance, and device registrations to understand customer behavior and trends affecting churn.

DAX Calculations

1. Customer Tenurity Classification
To determine the tenure of customers, the following DAX measures were used:

Minimum Tenure Customer = MIN('E Comm'[Tenure])

Median Tenure Customer = MEDIAN('E Comm'[Tenure])

Maximum Tenure Customer = MAX('E Comm'[Tenure])

Tenure Customer Range = IF('E Comm'[Minimum Tenure Customer] <= 10, "Bronze", IF('E Comm'[Median Tenure Customer] <= 20, "Silver", "Gold"))

- This classification helps categorize customers based on their tenure duration:
   Bronze: Customers with a tenure of 10 months or less.
   Silver: Customers with a median tenure of 20 months or less.
   Gold: Customers with longer tenures, indicating loyalty.

2. Warehouse to Home Distance Analysis
To analyze the relationship between warehouse-to-home distance and order frequency, the following DAX calculations were used:

Minimum distance from warehouse to home = MIN('E Comm'[Warehouse To Home])
Median Warehouse to Home = MEDIAN('E Comm'[Warehouse To Home])
Maximum distance from warehouse to home = MAX('E Comm'[Warehouse To Home])
Customer to warehouse Distance = IF('E Comm'[Minimum distance from warehouse to home] <= 20, "Near", IF('E Comm'[Median Distance from Warehouse to Home] <= 30, "Medium", "Far"))

- This classification helps in understanding how proximity to the warehouse impacts the number of orders placed:
   Near: Customers within 20 miles.
   Medium: Customers with a median distance of 30 miles or less.
   Far: Customers located beyond this range.

3. Average Number of Devices Registered
To identify the average number of devices per customer:

Average number of devices registered = AVERAGE('E Comm'[Number Of Device Registered])

This measure helps determine customer engagement across multiple devices, which may influence retention and churn rates.

Key Insights from the Report

- Tenure Impact: Customers with higher tenure (Gold category) are more likely to be retained, whereas newer customers (Bronze category) may have a higher churn rate.
- Distance Influence: Customers living closer to warehouses tend to place more orders compared to those who live farther away.
- Device Engagement: Customers registering multiple devices may indicate higher engagement, potentially reducing churn.

Potential Use Cases

Churn Prediction: Identifying customers who are likely to leave the platform.
- Customer Segmentation: Grouping customers based on demographics, purchasing behavior, and satisfaction levels.
- Personalized Marketing: Tailoring offers based on preferred order categories, payment modes, and login devices.
- Operational Optimization: Enhancing delivery efficiency by analyzing warehouse-to-home distances.
- Loyalty Program Enhancement: Improving cashback and coupon strategies based on past usage trends.

Conclusion

This analysis provides valuable insights for improving customer retention strategies by leveraging tenure, location, and device engagement data. Enhancing logistics and personalized engagement based on these findings can help Shop Sphere reduce customer churn and increase long-term loyalty.

File Information

Dataset Format: Excel (contains structured tabular data).
Report Format: Pbix (contains visual analytics and insights).

Contact & Further Analysis
For further data analysis and business insights, stakeholders can explore predictive modeling, trend analysis, and customer engagement strategies using tools like Python, Power BI, or SQL.
