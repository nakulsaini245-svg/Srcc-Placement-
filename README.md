# 📉 E-commerce Revenue Leakage & Seller Risk Audit
### *A Data Analytics Case Study by [Nakul Saini 25BC370]*

## 📌 Project Overview
This repository contains an end-to-end data analytics pipeline engineered using **Python (Pandas, NumPy, Matplotlib)** and **SQL**. The project analyzes platform transaction data to detect revenue leakage from Return-to-Origin (RTO) orders, quantifies financial loss across product categories, and establishes automated seller risk-tiering matrix models to preserve platform unit economics.

---

## 🛠️ Verification Mapping (CV Bullet Points vs. Implementation)

| CV Bullet Point | Technical Implementation & Code Evidence | Verified File / Output |
| :--- | :--- | :--- |
| **1. Python & SQL Data Pipelines for Revenue Leakage** | Aggregated `seller_metrics` to derive average and dynamic statistical thresholds (`danger_rto = mean_rto * 1.5`). Screened seller volumes with SQL `HAVING total_orders > 10`. | `project 1.py` (Lines 22–33)<br>`Sql Query 2.png` |
| **2. NumPy High-Value Segmentation (>₹30K)** | Categorized transactions using `np.where(df['order_value'] > 30000, 'High Value', 'Standard')` to isolate segment-wise RTO rates. | `project 1.py` (Line 8)<br>`Python Output.png` |
| **3. Matplotlib "Danger Zone" Matrix** | Plotted dynamic scatter matrix of Total Sales vs. RTO Rate with benchmark lines at Mean RTO (20.8%) and Danger Zone (31.2%). | `project 1.py` (Lines 36–52)<br>`Python Code figure.png` |
| **4. Seller Risk-Tiering Framework** | Evaluated high-risk sellers exceeding the 1.5x threshold (e.g., OmniTech at 37.32% RTO rate) vs. baseline sellers. | `Python Code figure.png`<br>`Python Output.png` |
| **5. Audit-Ready Loss Reports (SQL)** | Executed conditional SQL aggregation (`SUM(CASE WHEN is_rto = 1 THEN order_value...)`) to quantify exact category revenue losses. | `Sql Query 1 .png` |
| **6. Industry Benchmarking & Risk Lists** | Ranked seller risk profile across the platform to create actionable seller-onboarding and audit guidelines. | `Sql Query 2.png`<br>`Python Output.png` |

---

## 📊 Summary of Findings & Audit Outputs

### 1. Category Revenue Loss Breakdown (SQL Query 1 Output)
* **Fashion:** ₹16,08,574 loss (**27.22%** loss rate)
* **Beauty:** ₹15,24,059 loss (**20.72%** loss rate)
* **Electronics:** ₹13,51,138 loss (**20.53%** loss rate)
* **Home & Kitchen:** ₹9,01,080 loss (**14.49%** loss rate)

### 2. Seller Risk Audit Ranking (SQL Query 2 & Terminal Output)
* 🚨 **OmniTech:** 37.32% RTO Rate *(Flagged in Danger Zone > 31.2%)*
* ⚠️ **CloudTail:** 20.19% RTO Rate
* ⚠️ **Appario:** 18.81% RTO Rate
* 🟢 **RetailNet:** 16.59% RTO Rate
* 🟢 **SuperCom:** 11.11% RTO Rate
