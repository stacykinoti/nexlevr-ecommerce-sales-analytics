# Nexlvr E-Commerce Retail Sales & Customer Analytics

An end-to-end retail sales analytics project built with **Power BI Desktop**, **Power Query**, and **DAX**. This project analyzes commercial dataset performance across product categories, temporal seasonality, regional sales distributions, basket size benchmarks, and customer repurchase retention.

---

## 🖼️ Executive Dashboard Preview

![Dashboard Preview](dashboard/dashboard_preview.png)

---

## 📊 Key Business Findings

### 1. Top Products: Revenue vs. Unit Volume
* **Revenue Leader:** High-margin technology hardware leads total sales growth, anchored by the **3D Systems Cube Printer, 2nd Generation** (**\$9.1K** in revenue).
* **Volume Leaders:** High-frequency everyday office supplies (**Staples**) generate the highest physical transaction volume (**43 units**).

### 2. Monthly Trends & Q4 Seasonality
* Sales exhibit strong seasonal surges, peaking in **September** (**\$55K**), **November** (**\$52K**), and **December** (**\$52K**).
* Year-end promotional events drive a significant share of overall annual revenue.

### 3. Geographic Performance
* **East** and **West** regions represent the core revenue strongholds.
* **California** (**\$60.21K**) and **New York** (**\$49.07K**) stand out as the top individual state-level revenue drivers.

### 4. Average Order Value (AOV)
* The commercial retail benchmark for average basket spend is **\$468.00** per order.

### 5. Customer Retention & Repeat Revenue Share
* **61%** of overall revenue originates from returning customers (buyers with >1 completed transaction), demonstrating strong customer retention and repurchase value.

---

## 🛠️ DAX Measures Reference

### Average Order Value (AOV)
```dax
Average Order Value = 
DIVIDE(
    SUM(Cleaned_Superstore[Sales_Amount]), 
    DISTINCTCOUNT(Cleaned_Superstore[Order_ID]), 
    0
)
