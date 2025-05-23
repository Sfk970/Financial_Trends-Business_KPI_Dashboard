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

---

# 🔍 Step 1: SQL-Based Data Analysis

These SQL queries helped explore and understand the financial dataset before visualization.

### ✅ Insights Extracted Using SQL:

1. **YoY Revenue Growth per Company**
   - Query calculated year-wise revenue growth (%) for each company.

2. **Top 5 Companies by Average ROE**
   - Identified companies with the highest average Return on Equity.

3. **Companies with High ROE and Low Debt-Equity**
   - Filtered companies that had high ROE (above average) and a low debt-equity ratio.

4. **Category-Wise Average Net Profit Margin**
   - Displayed average profitability across different industry categories.

5. **Top 5 Companies by EBITDA Margin**
   - Ranked companies with the most efficient operations by EBITDA margin.

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
   - Exported to PDF and PBIX

---

## 💼 Resume & Portfolio Highlight

> Built a 2-page Power BI dashboard using 15 years of company financial data. Delivered executive-level insights on profitability, efficiency, and capital structure. Performed SQL-based exploration and used clean DAX logic to build stakeholder-ready visuals.

---

## 📁 File Structure

```bash
├── Financial_Trends_BI_Dashboard.pbix   # Power BI file
├── finance_dataset.csv                  # Dataset
├── README.md                            # Documentation
├── /images                              # Screenshots
