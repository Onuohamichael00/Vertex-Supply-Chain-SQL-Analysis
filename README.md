# Vertex Supply Chain Analysis

## Project Overview

This project analyzes supply chain and inventory data to evaluate supplier performance, product profitability, warehouse efficiency, shipment performance, transportation costs, and the financial impact of damaged inventory.

The analysis was developed using MySQL to answer key business questions and identify areas where management can improve profitability, reduce operational losses, and strengthen supply chain performance.

---

## Business Problem

Management needs better visibility into the financial and operational performance of its supply chain.

Although the business receives large volumes of inventory, not all products are sellable due to damage, while transportation and inventory costs also reduce overall profitability.

The key challenge is to understand which suppliers, products, categories, and warehouses are contributing the most value to the business and where operational inefficiencies are affecting profitability.


## Database Schema

The project uses a relational supply chain database consisting of three main tables:

### Suppliers

Contains information about the suppliers, including supplier name, country, rating, and lead time.

### Products

Contains product-level information including product name, category, supplier, unit cost, and selling price.

### Shipments

Contains shipment-level information including shipment date, warehouse, quantity received, quantity damaged, and transportation cost.

### Relationships

The tables are connected through primary and foreign keys:

SUPPLIERS → PRODUCTS → SHIPMENTS

Each product is associated with a supplier through `SUPPLIER_ID`, while each shipment is associated with a product through `PRODUCT_ID`.

The database schema can be found in:

`schema/create_tables.sql`

---

## Business Objectives

Management wants to understand:

1. Which suppliers contribute the most value to the business.
2. Which products generate the highest profits.
3. Which product categories perform best.
4. Which warehouses handle the largest inventory volumes.
5. How transportation costs affect profitability.
6. Which suppliers consistently perform well over time.
7. How shipment performance changes throughout the year.

---

## SQL Analysis

The analysis was divided into four main areas:

### 1. Business KPIs

The business KPI analysis measures overall supply chain performance, including:

- Total inventory received
- Total damaged products
- Damage rate
- Transportation cost
- Net units received
- Total inventory cost
- Potential revenue
- Net revenue
- Revenue lost due to damaged products
- Gross profit
- Net profit
- Profit margin

[View Business KPI SQL](sql/01_business_kpis.sql)


### 2. Product Analysis

Analysis of product profitability, loss-making products, category performance and product damage rates.

[View Product Analysis SQL](sql/02_product_analysis.sql)


### 3. Supplier Analysis

Analysis of supplier profitability, loss-making suppliers, supplier performance and transportation costs.

[View Supplier Analysis SQL](sql/03_supplier_analysis.sql)


### 4. Warehouse & Shipment Analysis

Analysis of inventory volumes, warehouse performance and shipment trends over time.

[View Warehouse & Shipment SQL](sql/04_warehouse_analysis.sql)

---

## Key Findings

### Inventory and Damage

The business received approximately **297,000 units of inventory**, of which approximately **289,000 units were undamaged and sellable**.

Approximately **7,500 units were damaged**, resulting in a **2.52% damage rate**.

The revenue impact of damaged inventory was approximately **400,000**, based on the difference between potential revenue and revenue generated from sellable products.

---

### Revenue and Profitability

Potential revenue, assuming every unit received could be sold, was approximately **15.4 million**.

After excluding damaged products, net revenue was approximately **15 million**.

Gross profit was approximately **6.8 million**.

After accounting for inventory costs and transportation costs, net profit was approximately **4.5 million**, producing an overall profit margin of approximately **30.48%**.

---

### Transportation Costs

Total transportation costs amounted to approximately **1.8 million**.

Transportation costs consumed approximately **12.52% of net revenue**, highlighting transportation as a significant cost affecting overall profitability.

The suppliers with the highest transportation costs were:

- Vertex Global Supply — 104,000
- Continental Traders — 103,000
- Pacific Source Ltd. — 102,000

---

### Product Performance

The most profitable products were:

1. Office Supplies Item 58 — 118,000
2. Kitchen Item 99 — 113,000
3. Kitchen Item 59 — 111,000
4. Home Appliance Item 57 — 110,000
5. Kitchen Item 39 — 104,918

Several products generated negative net profit, including products in the Electronics and Accessories categories.

The largest loss-making products included:

- Electronic Item 81
- Electronic Item 61
- Electronic Item 21
- Accessories Item 100
- Accessories Item 40
- Accessories Item 80
- Accessories Item 20
- Accessories Item 60

---

### Category Performance

The **Kitchen category** generated the highest net revenue at approximately **3.5 million**, followed by **Office Supplies** at approximately **3.2 million**.

This indicates that these categories are major contributors to overall business revenue.

---

### Supplier Performance

The most profitable suppliers were:

1. Metro Components — 495,000
2. Atlas Supply Group — 461,000
3. Sterling Manufacturing — 446,000
4. Excel Procurement — 412,000
5. Horizon Industrial Co. — 380,000

Two suppliers generated negative net profit:

- Alpha Manufacturing — **-782**
- Infinity Sourcing — **-30,000**

Supplier damage performance also revealed that **BluePeak Suppliers** supplied the highest number of damaged units at **458 units**, followed by Prime Components, Frontline Distributors, and Atlas Group Supply, each with approximately **450 damaged units**.

---

### Warehouse Performance

The **Ibadan and Abuja warehouses received the highest inventory volumes**, but despite handling large amounts of inventory, they generated the lowest net revenue.

The **Kano warehouse generated the highest net revenue**.

This suggests that inventory volume alone does not necessarily translate into stronger financial performance and that management should investigate differences in product mix, damage rates, selling performance, and operational efficiency between warehouses.

---

### Shipment Performance Over Time

Inventory receipts were highest during:

- August
- May
- April

The lowest inventory volumes were recorded during:

- October
- November
- December

Net revenue was strongest during:

- May — approximately 1.5 million
- April — approximately 1.43 million
- July — approximately 1.42 million

The weakest sales months were:

- November — approximately 1 million
- October — approximately 798,687
- December — approximately 796,478

---

## Recommendations

### 1. Reduce Transportation Costs

Management should review suppliers and shipment routes with disproportionately high transportation costs.

Negotiating better transportation agreements, consolidating shipments, and optimizing delivery routes could reduce transportation expenses and improve net profit.

### 2. Investigate Loss-Making Products

Products consistently generating negative net profit should be reviewed.

Management should evaluate their selling prices, unit costs, transportation costs, and damage rates to determine whether prices should be adjusted, suppliers renegotiated, or products discontinued.

### 3. Improve Damage Management

The 2.52% damage rate represents a significant operational and financial loss.

Management should investigate suppliers and shipment processes associated with high damage rates and introduce stronger packaging, handling, and quality-control procedures.

### 4. Review Underperforming Suppliers

Alpha Manufacturing and Infinity Sourcing generated negative net profit.

Management should review their purchasing costs, transportation expenses, product quality, and profitability before deciding whether to renegotiate contracts or reduce reliance on these suppliers.

### 5. Investigate Warehouse Efficiency

Ibadan and Abuja handled the highest inventory volumes but generated relatively low net revenue.

Management should investigate their product mix, inventory allocation, damage levels, and sales performance to determine why high inventory volumes are not translating into stronger revenue.

### 6. Prioritize High-Performing Categories and Products

The Kitchen and Office Supplies categories generated the strongest revenue.

Management should consider maintaining strong inventory availability for high-performing products while monitoring profitability to avoid excessive inventory accumulation.

### 7. Monitor Performance Throughout the Year

The significant variation in inventory receipts and net revenue across months suggests that management should use historical shipment and sales patterns to improve inventory planning and allocation.

---

## Tools & Technologies

- MySQL
- SQL
- MySQL Workbench
- GitHub

### SQL Concepts Used

- SELECT
- WHERE
- GROUP BY
- ORDER BY
- HAVING
- Aggregate Functions
- INNER JOIN
- Subqueries
- Derived Tables
- CASE
- Window Functions
- DENSE_RANK
- PARTITION BY

## Conclusion

The analysis shows that the business is profitable, generating approximately 4.5 million in net profit with an overall profit margin of 30.48%. However, the analysis also identified several opportunities to improve financial and operational performance.

Transportation costs, damaged inventory, loss-making products, underperforming suppliers, and differences in warehouse performance are the key areas requiring management attention.

Addressing these issues through improved transportation planning, stronger supplier management, better inventory controls, and product-level profitability analysis could help reduce avoidable costs and improve overall profitability.

---

## Project Structure

```text
Vertex-Supply-Chain-Analysis/
│
├── README.md
│
├── data/
│   ├── shipments.csv
│   ├── productskl.csv
│   └── suppliers.csv
│
├── schema/
│   ├── create_tables.sql
│   └── load_data.sql
│
└── sql/
    ├── 01_business_kpis.sql
    ├── 02_product_analysis.sql
    ├── 03_supplier_analysis.sql
    └── 04_warehouse_analysis.sql
