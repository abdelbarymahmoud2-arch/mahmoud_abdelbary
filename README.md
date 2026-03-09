# mahmoud_abdelbary
This repository contains an end-to-end ETL solution built using SQL Server Integration Services (SSIS). The project transforms transactional data into a dimensional model (Star Schema) to support business intelligence and reporting.

# ETL Data Warehouse Project: GravityBook
This repository contains an end-to-end ETL solution built using SQL Server Integration Services (SSIS). The project transforms transactional data into a dimensional model (Star Schema) to support business intelligence and reporting.
🚀 Project Overview
The goal of this project is to automate the movement of data from a source relational database into a structured Data Warehouse. It includes the implementation of Slowly Changing Dimensions (SCD Type 2) to maintain historical data and complex Lookups to populate Fact tables with appropriate surrogate keys.
# 🏗️ Architecture
The workflow follows a standard sequence to ensure data integrity:
Run Dimensions: Loading master data (Books, Authors, Customers, etc.).
Run Bridge: Handling many-to-many relationships (e.g., Book-Author bridge).
Truncate Facts: Preparing Fact tables for fresh data.
Run Facts: Loading transactional data into the Fact tables.
# 🛠️ Key Features
1. Dimension Loading (SCD Type 2)
For dimensions like Dim_Customer, Dim_Book, and Dim_Address, I implemented Slowly Changing Dimensions (SCD Type 2).
Historical Tracking: Captures changes over time by creating new records for updates.
Components: Uses SCD Wizard, Union All, and Derived Column transformations to manage StartDate, EndDate, and IsCurrent flags.
2. Fact Table Population
The Fact table loads (e.g., Fact_Sales and Order_History_Fact) utilize multiple Lookup Transformations to map business keys to surrogate keys from the dimension tables.
Lookups include: Date, Customer, Shipping Method, and Book dimensions.
Integrity: Ensures only records with valid dimensional references are loaded into the final destination.
3. Bridge Table Management
Includes logic to handle complex relationships, specifically for Dim_Book_Author, ensuring that many-to-many relationships between books and authors are correctly reflected in the warehouse.
# 📊 Technical Stack
Tool: SQL Server Integration Services (SSIS) / Visual Studio 2022.
Database: SQL Server (Source: Relational DB | Destination: Data Warehouse).
Transformations Used: * Lookup (Full Cache)
Slowly Changing Dimension (Type 2)
Derived Column
Union All
OLE DB Command (for updates)
# <img width="1557" height="880" alt="12" src="https://github.com/user-attachments/assets/6e27da14-2854-473b-8c23-0edf64a21740" />
<img width="1560" height="853" alt="11" src="https://github.com/user-attachments/assets/0730f264-c42d-4703-93e4-b8561f332386" />
<img width="1563" height="877" alt="1" src="https://github.com/user-attachments/assets/d21c5add-d1c7-4081-9697-f3bfbd80422d" />
🖼️ Screenshots
