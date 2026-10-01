# Brazilian E-Commerce Analytics & Customer Retention Pipeline (Olist)

An end-to-end business intelligence and data engineering pipeline transforming 100k+ Brazilian e-commerce transaction records into an analytical Star Schema, surface-level KPIs, and RFM customer segmentation.

---

## 📌 Executive Summary & Key Findings
* **Severe Repeat-Purchase Churn:** Analysis surfaced a repeat purchase rate of only **~3.0%**, indicating that ~97% of transactions are one-time acquisitions. Growth cannot rely purely on paid acquisition without post-purchase lifecycle re-engagement.
* **Geographic Logistics Bottlenecks:** Orders originating from outer states (North/Northeast regions) experienced delivery times exceeding **20–25 days**, directly correlating with lower satisfaction scores compared to São Paulo (`SP`) and Rio de Janeiro (`RJ`), which averaged **8–11 days**.
* **RFM Revenue Concentration:** "High-Value Champions" account for less than **5% of the total customer base** yet drive disproportionately higher Average Order Value (AOV) across core electronics and furniture categories.

---

## 🏗️ Architecture & Data Pipeline
1. **Raw Ingestion (Python ETL):** Automated extraction and transformation script (`etl_pipeline.py`) handling datetime normalization, unfulfilled order filtration, and staging schema deployment into PostgreSQL using `SQLAlchemy` and `Pandas`.
2. **Relational Modeling (PostgreSQL):** Denormalized raw staging structures into an OLAP **Star Schema** with an indexed fact table (`fact_orders`) and dimensional entities (`dim_customers`, `dim_products`).
3. **Advanced SQL (RFM Segmentation):** Implemented an analytical view using Common Table Expressions (CTEs) and `NTILE(4)` window functions scoring customers across Recency, Frequency, and Monetary tiers.
4. **BI & DAX Modeling (Power BI):** Direct database ingestion with custom DAX business logic tracking AOV, delivery latency, and cohort retention.

---

## 📊 Dashboard Previews

### Page 1: Executive Overview

*Tracks revenue trajectory, monthly transaction volume, average order values, and category-level gross revenue.*

### Page 2: Customer Retention & RFM Segmentation

*Surfaces retention drop-offs, customer RFM distributions, and regional delivery performance variations.*

---

## 🛠️ Tech Stack & Setup
* **Languages:** Python (Pandas, SQLAlchemy, psycopg2), SQL (PostgreSQL 16), DAX
* **Tools:** Power BI Desktop, pgAdmin 4, VS Code, Git/GitHub

### Reproducing Locally
1. Clone the repo:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/ecommerce-analytics-pipeline.git](https://github.com/YOUR_USERNAME/ecommerce-analytics-pipeline.git)
   cd ecommerce-analytics-pipeline
