# Financial_Trends-Business_KPI_Dashboard

This is a financial data analysis project based on data from major companies across industries between 2009–2023. The goal is to extract key financial insights and visualize them using Power BI. The project covers end-to-end steps including exploratory SQL analysis and interactive dashboard creation in Power BI.

-----

## 📌 Objective

To analyze long-term company financial data and deliver actionable business insights on revenue trends, profitability, efficiency, and capital structure using SQL and Power BI — without Python.

---

## 🛠 Tools Used

**SQL**: Exploratory analysis and filtering
**PowerBI**: Data modeling, DAX, dashboarding  

---

## 📂 Dataset Summary

- **Time Period**: 2009–2023  
- **Records**: 1200+  
- **Key Columns**: Company, Year, Category, Revenue, Net Income, ROI, ROE, Market Cap, EPS, EBITDA, Net Profit Margin, Debt-Equity Ratio, etc.
- **Source**: Data originally collected from [Kaggle](https://www.kaggle.com/datasets/rish59/financial-statements-of-major-companies2009-2023)

---

# 🔍 Step 1: SQL-Based Data Analysis

These SQL queries helped explore and understand the financial dataset before visualization.

### ✅ Insights Extracted Using SQL:

1. **YoY Revenue Growth per Company**
   - Query calculated year-wise revenue growth (%) for each company.
   - SELECT company, year, revenue,
    LAG(revenue) OVER (PARTITION BY company ORDER BY year) AS previous_year_revenue,
    ROUND(
        (revenue - LAG(revenue) OVER (PARTITION BY company ORDER BY year)) 
        / NULLIF(LAG(revenue) OVER (PARTITION BY company ORDER BY year), 0) * 100, 
        2
       ) AS yoy_revenue_growth_percent
       FROM financial_data
       ORDER BY company, year;


2. **Top 5 Companies by Average ROE**
   - Identified companies with the highest average Return on Equity.
   - select company, round(avg(ROE),2) as avg_ROE 
   from financial_data 
   group by company 
   order by avg_ROE desc 
   limit 5;

3. **Companies with High ROE and Low Debt-Equity**
   - Filtered companies that had high ROE (above average) and a low debt-equity ratio.
   - select company, category, year, ROE, DebtEquityRatio 
     from financial_data 
     where ROE>20 AND DebtEquityRatio<1 
     order by ROE desc;

4. **Category-Wise Average Net Profit Margin**
   - Displayed average profitability across different industry categories.
   - select category, round(avg(NetProfitMargin),2) as avg_Netprofit_margin 
     from financial_data 
     group by category
     order by avg_Netprofit_margin desc 

5. **Top 5 Companies by EBITDA Margin**
   - Ranked companies with the most efficient operations by EBITDA margin.
   - SELECT company,
    ROUND(AVG(ebitda / NULLIF(revenue, 0) * 100), 2) AS avg_ebitda_margin
    FROM financial_data
    GROUP BY company
    ORDER BY avg_ebitda_margin DESC
    LIMIT 5;
     

✅ These insights built a strong base for dashboard design in Power BI.

---

# 📊 Step 2: Power BI Dashboard

Using the cleaned dataset and SQL insights, a **2-page interactive dashboard** was built in Power BI.

---

## 📄 Dashboard Page 1 – Company-Level Financial KPIs

**Insights Visualized:**
1. Year-over-Year Revenue Growth by Company  
2. Top 5 Companies by Average ROE  
3. Companies with High ROE & Low Debt  
4. Top 5 by EBITDA Margin  
5. Category-Wise Average Net Profit Margin

---

## 📄 Dashboard Page 2 – Industry/Category Trends

**Insights Visualized:**
1. Category-Wise Total Revenue Over Years  
2. Top 5 Categories by Average ROI  
3. Debt-Equity Ratio by Category  
4. Yearly Market Cap Trends  
5. Category-Wise Average Net Income

---

## ❓ Stakeholder Questions Answered:

- Which companies are growing revenue consistently?
- Who are the most profitable companies?
- Which industries have the best ROI?
- How does debt usage vary across categories?
- What are the top sectors by market cap?

---

# ⚙️ Power BI Workflow Process

1. **Import CSV Dataset** into Power BI  
2. **Transform Data** in Power Query:
   - Checked nulls (one Market Cap value was set to `0`)
   - Verified column types
   - Removed duplicates

3. **Created DAX Measures**:
   - Revenue Growth %, Avg ROE, Avg ROI
   - Net Profit Margin, Debt-Equity Filter
   - EBITDA Margin, Top N Measures

4. **Visualized with Power BI Charts**:
   - Bar, Line, Stacked Columns, Cards
   - Slicers for Category and Year

5. **Dashboard Design**:
   - 2 Pages: Company View & Category View
   - Business-centric visual storytelling
   - Exported to PDF and PBIX.
