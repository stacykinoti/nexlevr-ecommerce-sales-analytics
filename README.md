# Nexlvr E-Commerce Retail Sales & Customer Analytics

An end-to-end retail sales analytics project built with **Power BI Desktop**, **Power Query**, and **DAX**. This project analyzes commercial dataset performance across product categories, temporal seasonality, regional sales distributions, basket size benchmarks, and customer repurchase retention.

---

## 🖼️ Executive Dashboard Preview

![Dashboard Preview](dashboard/dashboard_preview.png)

---

## 📊 Key Business Findings

### 1. Top Products: Revenue vs. Unit Volume
* **Revenue Leader:** High-margin technology hardware leads total sales growth, anchored by the **Canon imageCLASS 2200 Advanced Copier** (~\$61,599 in revenue).
* **Volume Leaders:** High-frequency everyday office supplies (**Binders** and **Paper**) generate the highest physical transaction volume.

### 2. Monthly Trends & Q4 Seasonality
* Sales exhibit strong fourth-quarter seasonality, peaking sharply in **November** and **December**.
* Q4 promotional demand accounts for **25%–30% of total annual revenue**.

### 3. Geographic Performance
* The **West Region** ranks #1 in overall revenue (**\$664,158 / 30.7% share**), closely followed by the **East Region** (**\$634,452 / 29.3% share**).
* **California** and **New York** represent the single largest state-level revenue drivers.

### 4. Average Order Value (AOV)
* The commercial retail benchmark for average basket spend sits between **~\$220 and \$230 per order**.

### 5. Customer Retention & Repeat Revenue Share
* **Over 75%** of overall revenue originates from returning customers (buyers with >1 completed transaction), demonstrating strong brand loyalty and high repurchase value.

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
Repeat Revenue Share = 
DIVIDE(
    CALCULATE(
        SUM(Cleaned_Superstore[Sales_Amount]), 
        FILTER(
            VALUES(Cleaned_Superstore[Customer_ID]), 
            CALCULATE(DISTINCTCOUNT(Cleaned_Superstore[Order_ID])) > 1
        )
    ),
    SUM(Cleaned_Superstore[Sales_Amount]),
    0
)