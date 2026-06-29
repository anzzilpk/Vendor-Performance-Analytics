Vendor Performance Analytics

A data analytics project that explores vendor and inventory data to evaluate vendor performance, profitability, and purchasing efficiency. Raw transactional data is loaded into a database, profiled through exploratory analysis, and rolled up into a vendor-level summary used to surface insights such as top/underperforming vendors, pricing efficiency, and inventory turnover.

Project Overview

Retail and wholesale businesses rely on dozens (or hundreds) of vendors, and inconsistent pricing, slow-moving inventory, or weak vendor relationships can quietly erode margins. This project works through that problem end-to-end:


Ingest raw vendor/sales/purchase data into a local database.
Explore the data to understand its structure, quality, and initial patterns.
Summarize the data into a single vendor-level table combining purchases, sales, and freight costs.
Analyze that summary to answer business questions about vendor and brand performance.


Repository Contents

FileDescriptioningestion_db.ipynbLoads raw source data (e.g. CSV files) into a database, used as the single source of truth for downstream analysis.Exploratory Data Analysis 2.ipynbInitial exploration of the ingested data — distributions, missing values, and early patterns across vendors, brands, and transactions.get_vendor_summary.pyBuilds a consolidated vendor summary table by joining purchase, sales, and freight data, then adds derived metrics (e.g. gross profit, profit margin, stock turnover).Vendor Perfomance Analysis.ipynbCore analysis notebook — uses the vendor summary to identify top and underperforming vendors/brands, pricing efficiency, and inventory trends, with supporting visualizations.

Key Questions Explored


Which vendors and brands contribute the most to sales and gross profit?
Which brands are underperforming and may need pricing or promotional changes?
How does bulk purchasing affect unit cost?
How efficiently is inventory turning over, and where is capital tied up in slow-moving stock?
How much profitability variance exists between high- and low-performing vendors?


Tech Stack


Python — data processing and scripting
Pandas — data manipulation and aggregation
SQLite (via sqlite3) — lightweight database for ingested data
Matplotlib / Seaborn — visualization (used in the notebooks)
Jupyter Notebook — exploratory and analytical work


Getting Started

Prerequisites


Python 3.x
Jupyter Notebook or JupyterLab
pandas, numpy, matplotlib, seaborn


bashpip install pandas numpy matplotlib seaborn jupyter

Running the Project


Clone the repository:


bash   git clone https://github.com/anzzilpk/Vendor-Performance-Analytics.git
   cd Vendor-Performance-Analytics


Place your source data (vendor purchases, sales, and invoice/freight CSVs) where ingestion_db.ipynb expects to find it, then run the notebook to load the data into a database.
Run Exploratory Data Analysis 2.ipynb to inspect the ingested data.
Run get_vendor_summary.py to generate the consolidated vendor summary table:


bash   python get_vendor_summary.py


Open Vendor Perfomance Analysis.ipynb to run the full vendor performance analysis and view the visualizations and insights.



Note: The raw dataset isn't included in this repository. Source your own vendor/purchase/sales data (this project follows the common "vendor inventory" dataset format used in similar analyses) and adjust file paths in ingestion_db.ipynb accordingly.



Possible Next Steps


Add a requirements.txt for reproducible environments
Externalize the database connection and file paths into a config file
Add a dashboard layer (e.g. Power BI/Tableau) on top of the vendor summary table
Package the summary logic into a reusable module rather than a standalone script


License

No license has been specified for this repository yet.
