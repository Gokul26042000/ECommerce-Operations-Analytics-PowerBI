# ECommerce-Operations-Analytics-PowerBI
# 📊 Brazilian E-Commerce Analytics Pipeline (Olist)
An end-to-end Power BI business intelligence suite analyzing 100K+ marketplace orders across commercial revenue, logistics pipelines, and customer satisfaction metrics.

## 🔗 Live Artifacts
* **Interactive Dashboard Portfolio:** [Insert NovyPro / LinkedIn Link Here]
* **Production Data Model File:** [`Click Here to Download .pbit`](BR_Ecom_Project.pbit)
* **Raw Data Source:** [Kaggle Olist Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

---

## 📌 Project Architecture & Business Strategy
This project translates raw transactional database tables into a centralized corporate reporting engine. Enterprise operations were split into three cross-functional domains to satisfy key corporate stakeholders:

├── Page 1: Executive Revenue & Growth Performance ──► Target: C-Suite (Macro Health)
├── Page 2: Logistics & Supply Chain Efficiency    ──► Target: Operations (SLA Tracking)
└── Page 3: Customer Experience & Quality Control  ──► Target: Product & Marketing (Retention)

### 🛠️ Data Engineering & ETL (Power Query)
* **Data Integration & Transformation:** Handled structural text inconsistencies, resolved null/missing keys in `product_category_name`, and mapped dimensional profiles.
* **Relational Star Schema:** Normalized flat files into a clean dimensional star schema model, isolating transactional Fact entity (`fact_order_items_dataset`) from Dimension tables (,`dim_orders_dataset`,`dim_customers_dataset`, `dim_products_dataset`, `dim_order_payments_dataset`,`dim_order_reviews_dataset`) via optimized primary and foreign key `1:M` relationships.

---

## 📋 Corporate Requirements & Visual Implementations

### Page 1: Executive Revenue & Growth Performance
* **BR-1.1 (High-Level KPIs):** Engineered high-level summary cards displaying Net Revenue, Total Sales, Average Order Value (AOV), and Total Units Sold.
* **BR-1.2 (Trend Analysis):** Built an active monthly time-series line chart tracking seasonal revenue vectors and peak order cycles.
* **BR-1.3 (Product Mix):** Configured a horizontal bar visual mapping the Top 10 Product Categories by revenue generation to identify dominant portfolio items.
* **BR-1.4 (Commercial Concentration):** Implemented a payment share donut chart detailing transaction methods (Credit Card vs. Boleto vs. Voucher vs. Debit Card).

<img width="1151" height="643" alt="image" src="https://github.com/user-attachments/assets/de69d421-af5e-4b3e-b425-118d8f2f815e" />


### Page 2: Logistics & Supply Chain Efficiency
* **BR-2.1 (KPIs):** Set up strategic scorecards calculating Average Days Taken for Delivery and the On-Time Delivery Rate.
* **BR-2.2 (SLA Gap Analysis):** Modeled a delivery variance calculator measuring the delta between Expected Delivery Date (EDD) and Actual Delivery Date (DD) to identify true delivery lag.
* **BR-2.3 (Geographic Performance):** Integrated an interactive geographical map mapping average logistics delays by customer state to isolate carrier bottlenecks.
* **BR-2.4 (Cost Metrics):** Designed a sales-to-freight cost ratio chart ensuring shipping overhead does not compress underlying product margins.

### Page 3: Customer Experience & Quality Control
* **BR-3.1 (KPIs):** Constructed a metric card reporting the core corporate benchmark: Overall Average Review Score (out of 5 stars).
* **BR-3.2 (Sentiment Distribution):** Restructured a rating standings bar chart utilizing explicit item volume counters (`COUNT` vs. `SUM`) to accurately report sentiment frequency distribution.
* **BR-3.3 (Correlation Insights):** Engineered a dual-axis trend graph cross-referencing average customer review scores with operational delivery delays, proving the **"Fulfillment Scissors Effect"** (where supply chain delay spikes directly trigger a crash in consumer sentiment).
* **BR-3.4 (Retention Tracking):** Formulated an advanced, multi-layered DAX measure to track customer loyalty across a complex relational star schema.

🔧 Engineering Log: Problem Solving & Debugging Case Study
"A project is only as good as the developer's ability to debug its hidden constraints."

During the initial build phase of Page 1, a critical discrepancy was uncovered where the core financial cards returned distorted, non-validated performance totals.

The Problem: The underlying data files contained hidden architectural anomalies (structural mismatches between transactional billing values and individual item price rows) that skewed the overall calculations.

The Diagnostic Process: Instead of relying on automated out-of-the-box defaults, I audited the data engine row-by-row, isolated the source data file bug, and mapped the mathematical variance independently.

The Resolution: Corrected the field mapping relationships, separated product item prices from raw invoice payment totals, and re-engineered the DAX measures to align with strict accounting logic. This ensured the dashboard reports verified business ground truth.
