data source: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce?resource=download
Data Architecture

The source data was loaded into Databricks Volumes and then processed using the Medallion Architecture approach
The data pipeline was divided into the following layers:
1. Bronze  raw data loaded directly from the source files. These tables represent the original input data and serve as the starting point for further transformations.
2. Silver cleaned and standardized data. Where necessary, I applied transformations such as data type conversions, null handling, duplicate removal, value standardization, and other data quality improvements.
3. Gold business-ready analytical tables prepared for reporting and data analysis. Based on the Silver layer, I created:
  - dim_* tables for dimensions,
  - fact_* / fct_* tables for facts.
The Gold layer was designed as an analytical data model and then connected to Power BI, where the tables are used to build relationships, measures, KPIs, and visualizations.

For example, in the sales schema, the pipeline includes Bronze and Silver tables as well as final Gold fact tables such as fct_orders, fct_items, and fct_payments.