# 📊 Retail Customer Behavior Analytics: End-to-End Data Pipeline

This project simulates an enterprise-grade data analytics workflow—from raw data extraction (ETL) and exploratory data analysis (EDA) to SQL-based modeling, data visualization, and strategic business recommendations.

## 1. Business Problem
A leading retail company aims to leverage transaction data to optimize sales, customer satisfaction, and long-term retention. With shifting purchasing patterns across demographics and channels, the core objective is to isolate variables driving consumer decisions—such as discounts, seasonality, and shipping methods.

Detailed business requirements can be found in: **`Retail_Analytics_Business_Case.pdf`**

## 2. Dataset Summary
*   **Source File:** `customer_shopping_behavior.csv`
*   **Volume:** 3,900 transactional records across 18 features.
*   **Dimensions:** Demographics, Order Details, and Behavioral Metrics.
*   **Baseline Metrics:** Average order value (AOV) of $59.76; average product rating of 3.75/5.

## 3. Tech Stack
*   **Python (Pandas, SQLAlchemy, PyODBC):** ETL pipeline, feature engineering, and database ingestion.
*   **MS SQL Server (T-SQL):** Relational database management and analytical querying (CTEs, Window Functions, Subqueries).
*   **Power BI:** Interactive dashboarding and business intelligence.

## 4. Project Workflow & Repository Structure

*   **`Customer_Shopping_Behavior_Analysis.ipynb` (Phase 1: ETL & EDA)**
    *   Loaded raw data and conducted initial data profiling.
    *   Handled missing `Review Rating` values via categorical median imputation.
    *   Engineered new features (`age_group`, `purchase_frequency_days`).
    *   Deployed `SQLAlchemy` to push the clean DataFrame directly into SQL Server.

*   **`customer_behavior_sql_queries.sql` (Phase 2: Data Analysis & Modeling)**
    *   Executed T-SQL scripts to aggregate revenue by demographic cohorts.
    *   Conducted customer segmentation (New, Returning, Loyal) based on historical purchase frequency.
    *   Analyzed discount dependency per product and evaluated AOV variances across shipping methods.

*   **`customer_behavior_dashboard.pbix` (Phase 3: Business Intelligence)**
    *   Deployed a dynamic dashboard with cross-filtering capabilities for membership status, gender, product categories, and shipping types.
    *   Visualized core KPIs and segment contributions using bar and donut charts.

## 5. Key Insights
*   **Revenue Distribution:** Male customers generated 68% of total revenue ($157k vs. $75k for females). The "Young Adult" segment drove the highest revenue volume ($62k).
*   **The Loyalty Paradox:** Despite a strong "Loyal" cohort (3,116 customers), 73% of the user base (2,847 users) remains unsubscribed.
*   **Spend Parity:** No statistically significant variance exists in AOV between subscribers ($59.49) and non-subscribers ($59.87).
*   **Product Performance:** "Clothing" leads total sales (~$100k). High discount dependency was observed in specific items: Hats (50%), Sneakers (49.6%), and Coats (49%).
*   **Shipping & Satisfaction:** "Express Shipping" correlates with a higher AOV ($60.48) compared to Standard shipping ($58.46). 

## 6. Actionable Recommendations
1.  **Overhaul Subscription Value Prop:** Target the massive pool of unsubscribed "Loyal" customers with exclusive perks to drive conversion.
2.  **Implement a Rewards Program:** Incentivize repeat purchases to transition "New" and "Returning" cohorts into the Loyal segment.
3.  **Optimize Promotional Strategy:** Restructure discount policies for highly dependent items (Hats, Coats) to protect profit margins.
4.  **Targeted Demographic Campaigns:** Focus marketing spend on the high-yield "Young Adult" segment, testing bundled offers that combine Express Shipping with membership.

*For the comprehensive analysis and presentation deck, please refer to:*
*   **`Customer Shopping Behavior Analysis.pdf`** (Full Report)
*   **`Customer_Shopping_Behavior_Analysis.pptx`** (Stakeholder Presentation)

## 🛠 How to Use
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  **Python Environment:** Run the `.ipynb` notebook to execute the ETL pipeline and load data into your local SQL Server instance.
3.  **SQL Environment:** Execute the `.sql` script in SQL Server Management Studio (SSMS) to review the analytical models.
4.  **Power BI Environment:** Open the `.pbix` file to interact with the visual dashboard.
