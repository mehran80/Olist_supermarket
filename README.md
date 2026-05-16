🚀 Brazilian E-Commerce End-to-End Data Pipeline & RFM Analytics
📝 Project Overview
This project demonstrates a professional End-to-End Data Engineering Pipeline using the Olist Brazilian E-Commerce dataset (100k+ orders). The goal was to transform raw, messy operational data into a high-performance Data Warehouse using a Star Schema and provide actionable business insights through RFM Customer Segmentation and Logistics Performance dashboards.
🏗️ Architecture (Medallion Architecture)
Bronze (Raw): 9 CSV files extracted and loaded into a PostgreSQL "Raw" database.
Silver (Cleaned/Modeled): Python (Pandas/SQLAlchemy) used for data cleaning, Portuguese-to-English translation, and logic-heavy transformations.
Gold (Analytics): High-value tables including a Star Schema (Fact/Dimension) and a specialized RFM Table for marketing automation.
🛠️ Tech Stack
Database: PostgreSQL (Operational & Data Warehouse)
Language: Python 3.x
Libraries: Pandas, NumPy, SQLAlchemy, Psycopg2
BI Tool: Power BI Desktop (DAX, Data Modeling)
📊 Data Modeling: The Star Schema
To optimize reporting performance, the data was remodeled from flat files into a Star Schema:
fact_sales: Contains transaction keys, price, freight, and calculated logistics KPIs (Delivery Gaps).
dim_products: Product attributes with English category translations.
dim_customers: Unique customer identification and geographic data.
gold_customer_rfm: A specialized table containing Recency, Frequency, and Monetary scores and segments (Champions, At Risk, Lost).
💡 Business Insights & KPIs
1. Logistics & Delivery Analysis
The "Delivery Gap" KPI: Engineered a column in Python to calculate the difference between Estimated and Actual delivery dates.
Finding: Identified specific Brazilian states where logistics bottlenecks were causing a high "Late Rate %."
2. RFM Customer Segmentation
Implemented an automated scoring system (1-5) to categorize the customer base:
Champions: High-frequency, high-spend customers.
At Risk: High-value customers who haven't shopped recently.
Lost: Low-engagement users.
Insight: Proved that the "Corporate" segment has a significantly higher Lifetime Value (LTV) than "Individual Consumers."
🚀 How to Run
Database Setup:
Create two databases in PostgreSQL: olist_raw and olist_warehouse.
Load the raw Olist CSVs into olist_raw.
Execute Pipeline:
Update the connection string in main.py.
Run python main.py to perform the ETL and create the Star Schema.
Visualization:
Open the .pbix file in Power BI.
Refresh the data to connect to your local PostgreSQL instance.
📸 Dashboard Preview
(Insert your screenshots here!)
![alt text](screenshots/dashboard_overview.png)
![alt text](screenshots/rfm_analysis.png)
![alt text](screenshots/logistics_map.png)
📂 Project Structure
code
Text
├── data/               # Raw Olist CSV files
├── scripts/            # Python ETL & RFM Logic
├── sql/                # Star Schema DDL & Integrity Checks
├── screenshots/        # Dashboard visuals for GitHub
├── reports/            # Power BI (.pbix) files
└── README.md           # Project Documentation
