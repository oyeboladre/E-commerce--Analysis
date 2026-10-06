# E-commerce--Analysis
SQL &amp; Python data analysis of the Olist Brazzilian E-Commerce dataset. Features data cleaning, relational joins, CTEs, window functions, and an interactive dark mode executive dashboard.
# 🛒 Olist E-Commerce: End-to-End Data Analysis & Business Insights

## 📖 Executive Summary
This project analyzes 100,000+ orders from the Olist Brazilian E-Commerce dataset. By combining SQL for complex aggregation and Python for visualization, I uncovered the root causes of revenue trends, logistical failures during peak seasons (Black Friday), and a critical customer retention gap. The final output is a comprehensive set of data-backed business recommendations.

## 🛠️ Tech Stack & Skills
*   Data Cleaning & Transformation: Python (Pandas, NumPy)
*   Business Logic & Aggregations: SQL (via pysqldf`), including CTEs, Window Functions (`ROW_NUMBER`), and `CASE statements.
*   Visualization: Plotly Express & Graph Objects.
*   Environment: Jupyter Notebook.

---

## 🧭 The Analysis Journey (STARR Method)

### 1. SITUATION (The Business Context)
Olist experienced explosive growth between 2016 and 2018. However, leadership lacked clarity on a critical question: *"Are we building a sustainable business, or are we just buying one-time transactions?"* Customer satisfaction was fluctuating, and the company needed to understand what was driving negative reviews and whether operational bottlenecks were hurting the bottom line.

### 2. TASK (The Goal)
The objective was to analyze 100,000+ orders across 9 relational tables to:
1. Identify the primary revenue drivers (what, when, and where).
2. Evaluate operational performance (delivery timelines and late rates).
3. Determine the root cause of negative customer reviews.
4. Assess customer loyalty and provide data-backed retention strategies.

### 3. ACTION (The Tracing Sequence)
Instead of looking at charts in isolation, I built a tracing sequence where every insight prompted the next question:

*   Tracing Step 1: What sells? I aggregated revenue by product category. health_beauty, watches_gifts, and bed_bath_table were the top revenue drivers.
*   Tracing Step 2: When do we sell? I plotted monthly revenue and found a massive, anomalous spike in November 2017.
*   Tracing Step 3: Was it Black Friday? I drilled into the daily data for November 2017. The highest revenue day was November 24, 2017 (Black Friday). This single day generated over R$1.2M in revenue.
*   Tracing Step 4: Can our logistics handle the spike? I calculated the Late Delivery Rate over time. The data showed a baseline late rate of 6.64%, which spiked precisely during Nov 2017 to 14.31%.
*   Tracing Step 5: Does being late hurt us? I joined the delivery dates with review scores. The result was undeniable: Orders delivered 1 day late received an average review score of 1 star, while early orders received 5 stars.
*   Tracing Step 6: Are customers coming back? I analyzed customer_unique_id to calculate the Repeat Buyer Rate. This exposed the core issue: Only 3.00% of customers ever make a second purchase.

### 4. RESULT (The Findings)
The analysis generated R$ 13.15M in total tracked revenue across 98,666 orders. However, the data revealed three critical business truths:
*   The Retention Crisis: With a 3% repeat buyer rate, the business is a "leaky bucket." However, the data shows that repeat buyers spend R$ 260.05 on average—an 81% increase over one-time buyers (R$ 137.96).
*   The Logistics Penalty: A single day of delay during peak season (Black Friday) is enough to destroy customer satisfaction.
*   The Weight Tax: Products over 5kg generate 1.5% more 1-star reviews and cost significantly more to ship.

### 5. RECOMMENDATION (The Business Strategy)

1.  Launch a Post-Purchase Retention Program (High Priority): 
    *   *The Data:* Repeat buyers are worth 81% more, but only 3% convert.
    *   *The Fix:* Implement an automated email sequence triggered 14 days after the first delivery. Offer a 10% discount on the second purchase. Capturing just 5% more repeat buyers would yield millions in additional lifetime value.
2.  Overhaul Peak Season Logistics & SLAs:
    *   *The Data:* Late deliveries tank reviews to 1 star.
    *   *   *The Fix:* During November (Black Friday), temporarily adjust the "Estimated Delivery Date" shown to customers by +3 days to buffer against courier network congestion. 
3.  Optimize Heavy Item Fulfillment:
    *   *The Data:* Heavy items have higher freight costs and lower review scores.
    *   *The Fix:* Audit the packaging and courier insurance for items >5kg. Consider offering "Free Shipping" on heavy items over a certain order value.

---

## 📊 Key Visualizations

1. Executive KPIs
![KPI Dashboard](images/01_kpi_dashboard.png)
*A summary of the most critical business metrics: Total Revenue, Total Orders, Average Review Score, and Average Freight Cost.*

2. Top 10 Product Categories by Revenue
![Top Categories](images/02_top_categories.png)
*Identifies the highest revenue-generating product categories, highlighting Health & Beauty as the top earner.*

3. Monthly Revenue Trend
![Monthly Revenue Trend](images/03_monthly_revenue_trend.png)
*Shows the explosive growth over time, with a massive, anomalous spike in November 2017 (Black Friday).*

4. Revenue Trend for Top 5 Categories (2016-2018)
![Top 5 Categories Trend](images/04_top5_categories_trend.png)
*Tracks the performance of the top 5 categories across different time periods, revealing a shift in consumer demand toward Health & Beauty.*

5. Top Product Category by State
![Top Category by State](images/05_top_category_by_state.png)
*Geographic analysis showing which product category dominates each state (e.g., Bed & Bath Table in São Paulo, Watches & Gifts in Rio de Janeiro).*

6. Total Orders by Product Weight and Review Score
![Weight vs Review Score](images/06_weight_review_score.png)
*Reveals the "Weight Tax": heavier items (>5kg) have a larger proportion of 1-star reviews compared to lighter items.*

7. Top 5 Product Categories by Weight Class
![Categories by Weight](images/07_categories_by_weight.png)
*Breaks down product categories into Light, Medium, and Heavy classes, providing a blueprint for logistics planning.*

8. Delivery Performance: On-Time vs Late Over Time
![Delivery Performance](images/08_delivery_performance.png)
*Visualizes the late delivery rate, confirming that the logistics network was overwhelmed during the Nov 2017 Black Friday event.*

9. Customer Loyalty: Volume vs Value
![Customer Loyalty](images/09_customer_loyalty.png)
*The core retention insight: While One-Time Buyers dominate volume, Repeat Buyers spend 81% more on average. *

---

## 📂 Repository Structure
*   Untitled21.ipynb - Full Python and SQL analysis pipeline.
*   images/ - Screenshots of key visualizations.
*   README.md - Project documentation.
