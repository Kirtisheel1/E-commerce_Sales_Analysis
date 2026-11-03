# E-Commerce Business Performance Analysis (2024-2025)

An end-to-end data engineering and analytics pipeline evaluating sales growth, category trends, and acquisition channels.

---

## 📌 Project Overview
This project processes raw transactional data from an e-commerce platform to extract meaningful insights about revenue trends, year-over-year (YoY) performance, product popularity, and marketing channel ROI. 

Our data pipeline features advanced preprocessing, including **pre-merge data deduplication** and **imputed pricing recovery** to ensure extreme accuracy in final financial evaluations.

---

## 🗃️ Datasets Used
- **`customers.csv`**: Demographics and acquisition channels (3,600 users).
- **`orders.csv`**: Transaction statuses, dates, and payment types (9,245 orders).
- **`order_items.csv`**: Order line items, quantities, unit prices, and discounts (15,608 entries).
- **`products.csv`**: Comprehensive product catalog with MSRP list pricing and catalog unit costs.

---

## ⚙️ Data Pipeline & Integrity Checklist

1. **Handling Missing Prices (Imputation)**
   - Rather than discarding valuable order items with missing prices, we mapped their `product_id` against the catalog MSRP list price (`df_prod`) to impute missing `unit_price` fields.

2. **Deduplication**
   - Deduplicated raw orders data (`df_ord`) prior to table joins to prevent synthetic row amplification and inflated financial calculations.

3. **Financial Feature Engineering**
   - Built custom metric tracking:
     Revenue = (Quantity * Unit Price) - Discount Amount

4. **Time & Visualization Mapping**
   - Parsed raw string dates into structured datetime fields and utilized month abbreviation mapping (e.g. Jan - Dec) on plots for streamlined readability.

---

## 📈 Executive Summary (Key Business Findings)
- **Consistent Growth:** Top-line company revenue experienced strong growth, jumping **21%** YoY from **$926.5k** in 2024 to **$1.12M** in 2025.
- **Furniture Powerhouse:** The **Furniture** category drove the highest single-category volume ($177k in 2025), while **Storage** was our fastest growing segment (surging YoY from $57k to $80.9k).
- **Acquisition Engines:** **Organic Search** generated nearly 68% ($762.3k) of company-wide sales, whereas **Paid Search** drove the highest Average Order Value (AOV) at **$229.25** per transaction.

---

## 🚀 Next-Steps & Business Strategy
1. **Protect Organic Real Estate:** Prioritize content marketing and SEO infrastructure to safeguard Organic Search traffic since it serves as our primary revenue driver.
2. **Target High-AOV Ad Spending:** Funnel Paid Search advertising budgets directly into **Furniture, Bedding, and Decor** to capture higher transaction margins from high-intent buyers.
