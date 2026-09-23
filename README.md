 PLSQL Assignment One 
SUN RISE SUPER MARKET

Name: Ihirwe Benie
Student ID: 28806
DBMS Used: PostgreSQL

Business Scenario
Sunrise Supermarket tracks products sold to customers who place orders containing one or more items. Management wants to understand customer demographics, purchasing habits, and sales trends over multiple dates.

Database Setup
The database includes tables for customers, products, categories, orders, and order items, populated across multiple dates.

Queries & Explanations

•	Customer Spending Rank
Query Goal: Ranks customers based on their total spending using window functions.
SQL Logic: Utilizes SUM() aggregated by customer and the RANK() window function ordered by total spend descending.

•	Running Total of Revenue
Query Goal: Calculates the cumulative revenue growth over time.
SQL Logic: Uses SUM() as a window function combined with OVER (ORDER BY order_date ASC).

•	Days Between Current and Previous Order
Query Goal: Finds the time gap between consecutive orders for customers with more than one order.
SQL Logic: Implements a CTE with the LAG() window function to grab the previous order date, filtering for customers with total_orders > 1.

Results & Screenshots


Business Interpretation

•	Tracking order frequency using date gaps helps identify customer loyalty trends.
•	Running totals assist management in observing long-term sales momentum.

 Challenges & Resolutions

<img width="688" height="306" alt="Screenshot 2026-09-19 110059" src="https://github.com/user-attachments/assets/afd1579c-85dc-41a3-8a25-d08d3a7778cc" />
<img width="798" height="498" alt="Screenshot 2026-09-19 110223" src="https://github.com/user-attachments/assets/e2f16bf0-4326-4672-8d6c-7d71de0f6ea4" />
<img width="829" height="416" alt="Screenshot 2026-09-19 110302" src="https://github.com/user-attachments/assets/7c597b67-8529-40db-9a3e-613fc6196f29" />





 
Challenge: Handling missing table/column references (such as direct revenue columns).
Resolution: Used table joins across orders, order_items, and products to properly calculate revenue on the fly. 
