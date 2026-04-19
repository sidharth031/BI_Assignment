<h1 align="center">📊 Fabric Sales Analytics</h1>
<h3 align="center">End-to-End Microsoft Fabric + Power BI Project</h3>

<p align="center">
  <b>Lakehouse • Dataflow Gen2 • DAX • Calculation Groups • Advanced Analytics</b>
</p>

---

## 🌟 Project Overview

This project demonstrates a **complete end-to-end analytics solution** using **Microsoft Fabric and Power BI**.

🎯 Objective:
- Analyze retail sales data  
- Deliver actionable business insights  
- Build a scalable modern data solution  

🔍 Key Focus Areas:
- 📈 Sales trends and performance  
- 🛍️ Product & brand contribution  
- 👥 Customer retention and segmentation  
- ⚙️ Operational efficiency  

📌 Architecture:
> **Lakehouse → Semantic Model → Interactive Dashboard**

---

## 🏗️ Architecture
Excel → Dataflow Gen2 → Lakehouse (Delta Tables)
↓
Power BI Semantic Model (Star Schema)
↓
Interactive Dashboard

| Layer | Tool | Description |
|------|-----|------------|
| Ingestion | Dataflow Gen2 | Power Query transformations |
| Storage | Fabric Lakehouse | Delta tables (Silver layer) |
| Modeling | Power BI | Star schema + relationships |
| Reporting | Power BI | Interactive dashboards |

---

## 📂 Dataset

📁 Source: Excel dataset (Sales Data for Fabric)

Includes:
- Sales transactions  
- Product hierarchy (Item, Category, Brand)  
- Customer data  
- Geography data  

---

## 🔄 Data Ingestion

**✅ Path Used: Dataflow Gen2**

- Excel file uploaded to Fabric Lakehouse  
- Data transformed using Power Query  
- Output stored as Delta tables:
silver_Sales
silver_Item
silver_Customer
silver_Geography
dim_Date

---

## 🧱 Data Model (Star Schema)
               dim_Date
                   |
silver_Item — silver_Sales — silver_Customer
                  |
            silver_Geography

### ⭐ Fact Table
- `silver_Sales`

### ⭐ Dimension Tables
- `silver_Item`
- `silver_Customer`
- `silver_Geography`
- `dim_Date`

### 🔗 Relationships
- Sales → Item (ItemKey)  
- Sales → Customer (CustomerKey)  
- Sales → Geography (CityId)  
- Sales → Date (OrderDate)  

---

## 🔧 Data Transformations

### 🧵 Item Dimension
- Merged Item Part 1 & Item Part 2  
- Removed empty rows  
- Handled missing BrandId using Fill Down logic  
- Joined with Category, Brand, SubCategory  

### 👤 Customer Dimension
- Removed duplicate CustomerKey  
- Created AgeGroup column:
  - Under 25  
  - 25–44  
  - 45–64  
  - 65+  

### 🌍 Geography Dimension
- Deduplicated GeographyKey  
- Standardized city and state names  

### 💰 Sales Table
Created calculated columns:
- Gross Amount  
- Discount Amount  
- Net Amount  
- COGS Amount  
- Margin  
- Delivery Delay  

### 📅 Date Table
- Generated dynamically using min/max OrderDate  
- Includes:
  - Year, Quarter, Month, Month Name  
  - Week, Day of Week  
  - Weekend flag  
  - Fiscal Year  

---

## 📐 DAX & Analytics

### 🔹 Base Measures
- Gross  
- Net  
- Discount  
- COGS  
- Margin  
- Margin %  
- Discount %  

### 🔹 Time Intelligence
- MTD, QTD, YTD  
- Prior Month  
- Rolling 3 Months  
- Year-over-Year (YoY %)  
- Month-over-Month (MoM %)  

### 🔹 Customer Analytics
- Cohort Analysis  
- Customer Retention Rate  
- RFM Segmentation:
  - Recency  
  - Frequency  
  - Monetary  

### 🔹 Advanced Analytics
- ABC Classification (A/B/C segmentation)  
- Pareto Analysis  

---

## ⚙️ Calculation Groups (Advanced)

Implemented using **Tabular Editor**

### 🕒 Time Intelligence
- Actual  
- MTD  
- QTD  
- YTD  
- Prior Month  
- Rolling 3M  
- YoY %  

### 📊 Metrics Switching
- Gross  
- Net  
- Margin  
- Discount  

💡 Benefits:
- Reduced number of measures  
- Dynamic report switching  
- Improved model efficiency  

---

## 📊 Dashboard Pages

### 🏠 1. Executive Overview
- KPI Cards (Net Sales, Margin %, MoM %)  
- YoY Sales Trend  
- Map: Sales by State  
- Dynamic slicers (Year, Category, Brand)  

---

### ⏱️ 2. Time Insights
- Time Intelligence using Calculation Groups  
- Rolling 3M trend  
- Delivery delay analysis  

---

### 👥 3. Cohort & Customer
- Cohort retention matrix  
- Retention by Age Group  
- RFM customer segmentation  

---

### 📦 4. ABC Classification
- A/B/C classification of products  
- Revenue contribution analysis  

---

### 📍 5. Quadrant Analysis
- Discount % vs Margin % scatter plot  
- Profitability segmentation  

---

### 🧠 6. Advanced Analysis
- Decomposition Tree (drill-down insights)  
- Gap analysis (unsold products)  
- Dynamic measures via field parameters  

---

### 🔝 7. Top / Bottom Analysis
- Top & Bottom products and brands  
- Margin % and Discount % comparison  
- Drill-through and tooltips  

---

## 📌 Key Insights

✨ Insights derived from analysis:

- A small number of products contribute most of the revenue (**Pareto Principle**)  
- High discounts significantly reduce margins  
- Customer retention decreases over time after first purchase  
- Age group **25–44 shows higher retention**  
- Certain brands dominate overall sales  

---

## ✅ Validation

✔ Relationships validated  
✔ No duplicate keys in dimensions  
✔ Measure checks:
- Net = Gross - Discount  
- Margin = Net - COGS  

✔ Date table covers full data range  

---

## 🛠️ Tools & Technologies

- Microsoft Fabric  
- Power BI  
- DAX  
- Dataflow Gen2  
- Tabular Editor  

---

## 🚀 Future Improvements

- 🔄 Incremental data refresh  
- ⚡ Real-time data ingestion  
- 🤖 Predictive analytics using Machine Learning  

---

## 👨‍💻 Author

**Sidharth Joshi - Software Engineer Intern**  
📅 April 2026  

---

⭐ If you found this project useful, consider giving it a star!
