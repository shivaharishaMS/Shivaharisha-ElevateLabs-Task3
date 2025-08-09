# Shivaharisha-ElevateLabs-Task3
# Walmart Sales Dashboard — Power BI

**Internship Task**  
Interactive Power BI dashboard to analyze Walmart weekly sales data.

---

## 🔎 Project Overview
This project builds an **interactive dashboard in Power BI** using the `Walmart_Sales.csv` dataset.  
The dashboard delivers KPIs, time-series trends, store performance comparisons, and holiday impact analysis — all with dynamic filtering.

---

## 📁 Dataset
- **Dataset Name:** `Walmart_Sales.csv`
- **Fields:**
  - `Date` → Date format
  - `Store` → Integer
  - `Weekly_Sales` → Decimal
  - `Holiday_Flag` → Integer (0 = Normal week, 1 = Holiday week)
  - Additional: `Temperature`, `Fuel_Price`, `CPI`, `Unemployment`

---

## 🎯 Objective
The main goal is to:
- Track total & average weekly sales
- Compare store-level performance
- Identify holiday week impact on revenue
- Enable interactive filtering by store, date, and holiday type

---

## 🛠️ Tools
- **Power BI Desktop** — Dashboard development
- **Microsoft PowerPoint** — Summary presentation
- **GitHub** — Version control & project sharing

---

## 🧭 Steps Followed

1. **Data Import**
   - Home → Get Data → Text/CSV → `Walmart_Sales.csv`

2. **Data Cleaning (Power Query)**
   - Change `Date` to **Date type**
   - Change `Weekly_Sales` & numeric fields to **Decimal Number**
   - Change `Holiday_Flag` to **Whole Number**
   - Remove duplicates if found

3. **Data Modeling**
   - Create DAX measures:
     ```DAX
     Total Sales = SUM(Walmart_Sales[Weekly_Sales])
     Average Sales = AVERAGE(Walmart_Sales[Weekly_Sales])
     Holiday Sales = CALCULATE(SUM(Walmart_Sales[Weekly_Sales]), Walmart_Sales[Holiday_Flag] = 1)
     Store Count = DISTINCTCOUNT(Walmart_Sales[Store])
     ```
   - Create calculated columns:
     ```DAX
     Month = FORMAT(Walmart_Sales[Date], "MMM")
     Month Number = MONTH(Walmart_Sales[Date])
     Holiday Type = IF(Walmart_Sales[Holiday_Flag] = 1, "Holiday", "Normal Week")
     ```
     Set `Month` to **Sort by Column → Month Number**

4. **Visualization**
   - **KPIs:** Total Sales, Average Sales, Holiday Sales, Store Count
   - **Line Chart:** Weekly Sales over time
   - **Column Chart:** Monthly Total Sales
   - **Bar Chart:** Sales by Store
   - **Table:** Detailed data view
   - **Slicers:** Store, Date Range, Holiday Type

5. **Formatting**
   - Apply consistent theme & font
   - Use readable axis labels & legends
   - Align slicers & visuals for clarity

---

## 📊 Key Insights
- Sales have seasonal peaks around holidays
- Top-performing stores maintain consistent high weekly sales
- Holiday weeks significantly boost total revenue

---
