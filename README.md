# Customer Shopping Behavior Analysis

Professional data analytics project showcasing end-to-end analysis of e-commerce customer behavior using Python, SQL and Power BI.

## Overview

This project analyzes 3,900 customer transactions from an online retail store to uncover insights about:

- Spending patterns by gender, age group and subscription status
- Product preferences and category performance
- Impact of discounts, shipping types and customer loyalty
- Review ratings and repeat purchase behavior

The main goal was to transform raw transactional data into clear, actionable business recommendations.

## Dataset

- **Source**: Synthetic / anonymized e-commerce transactions  
- **Size**: 3,900 rows × 18 columns  
- **Key columns**:
  - Customer demographics: age, gender, location, subscription_status
  - Purchase details: item_purchased, category, purchase_amount, season, size, color
  - Behavior: discount_applied, promo_code_used, previous_purchases, frequency_of_purchases, review_rating, shipping_type

No missing values in the original dataset.

## Tools & Technologies

| Stage                | Tools / Technologies                     |
|----------------------|------------------------------------------|
| Data loading & EDA   | Python · pandas · numpy                  |
| Data cleaning        | Python · pandas                          |
| SQL analysis         | PostgreSQL · pgAdmin / DBeaver           |
| Visualization        | Power BI                                 |
| Report & slides      | Gamma.app (AI-assisted presentation)     |
| Version control      | Git                                      |

## Project Steps

1. **Data Acquisition & Loading**  
   - Imported CSV file into Jupyter Notebook using pandas

2. **Exploratory Data Analysis (EDA)**  
   - Descriptive statistics (`df.describe()`, value counts)  
   - Distribution of numerical & categorical variables  
   - Initial visualization (histograms, boxplots, countplots)

3. **Data Cleaning & Feature Engineering**  
   - Standardized column names (snake_case)  
   - Created `age_group` bins  
   - Derived purchase frequency logic  
   - Removed redundant column (`promo_code_used` after consistency check)

4. **Database Integration**  
   - Loaded cleaned DataFrame into PostgreSQL table  
   - Used SQLAlchemy / psycopg2 for connection

5. **SQL Analysis** (10+ business questions)  
   - Revenue by gender / age group  
   - Subscription vs non-subscription spending  
   - Top products by rating / sales volume  
   - Discount dependency by item  
   - Customer segmentation (New / Returning / Loyal)  
   - Average spend by shipping type  
   - Repeat buyer behavior by subscription status

6. **Visualization & Dashboard**  
   - Built interactive Power BI dashboard  
   - Key visuals: bar charts, pie charts, treemaps, KPI cards  
   - Filters: category, age group, subscription status, shipping type

7. **Reporting & Presentation**  
   - Compiled detailed PDF report (insights + recommendations)  
   - Created executive summary presentation using Gamma.app

## Key Results & Business Insights

- ~68% of revenue comes from male customers
- Clothing & Accessories dominate sales volume and value
- Young Adults (26–27%) slightly lead revenue, but distribution across age groups is quite balanced
- Only 27% of customers are subscribers (big growth opportunity)
- Very high retention: ~80% of customers are classified as Loyal
- Average review rating: 3.75 → room for quality/experience improvements
- High discount dependency on several clothing items (risk to margins)

## Business Recommendations (summary)

- Aggressively grow subscription base (target repeat non-subscribers)
- Strengthen new customer acquisition (currently only ~2%)
- Gradually reduce extreme discounts (>45–50%) on top items
- Prioritize Clothing & Accessories in marketing & inventory
- Improve review scores through better photos, sizing info & post-purchase follow-up

## How to Run / Reproduce

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/customer-shopping-analysis.git
cd customer-shopping-analysis

# 2. Install dependencies (recommended: virtual environment)
pip install -r requirements.txt

# 3. Prepare PostgreSQL
#    • Create database "shopping_analysis"
#    • Update connection string in notebook (or .env file)

# 4. Run the main notebook (order matters)
jupyter notebook 01_data_prep_eda.ipynb
jupyter notebook 02_sql_analysis.ipynb
# (Power BI file and Gamma presentation are static exports)
