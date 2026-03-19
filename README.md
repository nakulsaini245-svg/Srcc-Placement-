# 📉 E-commerce Revenue Leakage & Seller Risk Audit
### *A Data Analytics Case Study by [Nakul Saini 25BC370]*

## 🚀 The Business Problem
E-commerce platforms lose millions due to **RTO (Return to Origin)**. My goal was to identify which categories and sellers are the biggest "Profit Killers."

## 🛠️ Tech Stack
* **SQL (SQLite):** For data extraction and revenue loss calculations.
* **Python (Pandas/NumPy):** For segmenting high-value orders.
* **Matplotlib:** For building the **Seller Health Matrix**.

## 📊 Key Insights
* **Risk Thresholding:** Established a "Danger Zone" (1.5x Mean RTO) to flag high-risk sellers.
* **Segmentation:** Found that "High-Value" orders (>30k) have a significantly different risk profile than standard orders.
