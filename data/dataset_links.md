# Dataset Information & Source Links

## Primary Dataset: Superstore Dataset
- **Data Source:** [Superstore Dataset (Final) on Kaggle](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)
- **File Name:** `Sample - Superstore.csv`
- **Dataset Size:** 9,994 rows × 21 columns
- **Description:** Comprehensive commercial retail records detailing sales, profits, customer segments, product categories, and geographical distributions.

## Key Data Preprocessing & Cleaning Rules
1. **Missing ID Filtering:** Filtered out `NULL` and blank `Customer ID` records to protect retention metrics.
2. **Order Prefix Auditing:** Verified valid regional order prefixes (`CA-` and `US-`).
3. **Data Type Casting:** Cast `Order Date` and `Ship Date` to native Date types; verified `Sales` and `Profit` as numeric decimals.
4. **Text Standardisation:** Applied `Trim` and `Capitalize Each Word` to `City`, `State`, `Region`, `Category`, and `Sub-Category`.
5. **Header Standardisation:** Renamed space-separated column headers to clean `snake_case` / `Pascal_Snake_Case` formatting (`Order_Date`, `Customer_ID`, `Sales_Amount`).