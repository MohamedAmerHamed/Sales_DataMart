# Sales_DataMart
 A Sales Data Mart stores and analyzes sales data from sources like transactions, customers, and products. Using an ETL process, data is cleaned and organized into tables, often in star or snowflake schemas. This helps businesses analyze sales trends and make informed decisions.

Overview of the Sales Data Mart with SSIS
A Sales Data Mart aggregates and stores data related to sales transactions, customer information, and product details. SSIS is a powerful ETL (Extract, Transform, Load) tool in SQL Server, which helps automate the process of extracting data from various sources, transforming it into a usable format, and loading it into a destination (such as a SQL Server database).

Steps to Create a Sales Data Mart Using SSIS
Extract Data (E in ETL)

Source Systems: Data is extracted from various data sources, such as:
Sales transactions from a transactional database (e.g., SQL Server, Oracle).
Customer data from CRM systems or customer databases.
Product details from inventory management systems or product catalogs.
SSIS Source Components: Use OLE DB Source, Flat File Source, or SQL Server Source to connect to and extract data from these systems.
Transform Data (T in ETL)

Data Cleaning: This involves removing duplicates, correcting errors, and handling missing data (e.g., filling null values with defaults).
Data Mapping: Transform the data into a suitable format for the data mart. This includes converting date formats, aggregating numerical values (like total sales per product), or calculating derived columns (like profit margins).
SSIS Transformation Components:
Data Conversion: Converts data types (e.g., converting string data to numeric).
Derived Column: Creates new columns based on expressions or calculations (e.g., total sales = quantity * unit price).
Lookup: Used to fetch data from dimension tables like time or customer details to enrich fact data.
Aggregate: Groups data for aggregation (e.g., summing sales by product or customer).
Load Data (L in ETL)

Destination: After transforming the data, it’s loaded into a structured data mart, typically using a SQL Server database with star or snowflake schemas.
Fact Tables: Contain quantitative data such as sales amount, quantities sold, profit, etc.
Dimension Tables: Contain descriptive data such as customer details, product categories, time, and location.
SSIS Destination Components: Use OLE DB Destination, SQL Server Destination, or Flat File Destination to load the transformed data into the data mart.
Handling Incremental Loads (if applicable)

Incremental Load: Instead of loading all data each time, you can load only the new or changed data since the last update. This can be done by using SSIS Lookup and Data Flow components like Conditional Split or by checking timestamps or change data capture (CDC).
Data Warehousing Schema (Star or Snowflake Schema)

In a Star Schema:
Fact Table: Stores metrics (e.g., sales quantity, sales revenue).
Dimension Tables: Contain descriptive data (e.g., customer, time, product).
In a Snowflake Schema: Dimension tables are normalized into multiple related tables (e.g., splitting customer details into address, demographic information).
Source: https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2012.bak
