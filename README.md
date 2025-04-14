

# Crowdfunding_ETL

**Project Overview** 

The goal of this project is to *extract* data from Excel files, *transform* the data into a structured format, *create* a relational database, and load the *transformed* data into it.

**Group members**
- Asif Shehzad
- Ilknur 
- Jose Traboulsi
- Seyhr Waqas

## Data Extraction and Transformation

**Category and Subcategory DataFrames:**

In this project we extracted *categories and subcategories* from the 'category & sub-category' column in the crowdfunding Excel file provided in resources folder.

**Created Category DataFrame** which Contains *category_id* and *category names*. There are total *9* categories in the dataframe. 

![Categories Dataframe](https://github.com/user-attachments/assets/6c871262-1774-4d8a-8ce8-69f3672b4625)


**Created Subcategory DataFrame** which Contains *subcategory_id* and *subcategory names*. There are total *24* sub-categories in the dataframe.

![Sub-categories Dataframe](https://github.com/user-attachments/assets/eef4a261-3bbc-4def-ba5d-cdce42de65a7)

Exported these dataframes as 'category.csv' and 'subcategory.csv' separately.


**Campaign DataFrame:**

1. *Transformed* the crowdfunding data by renaming the columns 'blurb' to 'description', 'launched_at' to 'launch_date', 'deadline' to 'end_date'.

   ![Renamed Colums](https://github.com/user-attachments/assets/786a1a1e-40cb-4e9f-9699-5907bb60958d)


3. *Converted* 'goal' and 'pledged' to float type.

   ![Datatypes](https://github.com/user-attachments/assets/0d9287d8-7ef6-410d-996a-b4d0efb54ef2)

5. *Converted* 'launch_date' and 'end_date' from Unix timestamps to datetime format

![Dates in Unix timestamps](https://github.com/user-attachments/assets/b47bc764-4e9b-478b-82f1-0d5482597bc9)

![Datetime format](https://github.com/user-attachments/assets/2a2a930f-6bb2-4db7-9a09-e633e745fec4)

Exported the dataframe as 'campaign.csv'.

**Contacts DataFrame:**

*Extracted* contact data from the contacts Excel file.

*Created* a DataFrame with *Contact_id, First_name, last_name, email*

![contacts details](https://github.com/user-attachments/assets/87c0591f-97e3-4de8-97ec-7e260070ed02)


Exported data as 'contacts.csv'.

## Database Design:

**Entity Relationship Diagram (ERD):**

Designed an ERD to represent relationships between tables:
Category: Primary key is 'category_id'
Subcategory: Primary key is 'subcategory_id'
Contacts: Primary key is 'contact_id'
Campaign: Primary key is 'cf_id', with foreign keys referencing other tables

![ERD](https://github.com/user-attachments/assets/3f917afe-6bb9-4e93-8b43-c261eb774c04)

## Data Schema:
Created a *PostgreSQL database* named 'crowdfunding_db'.

![Database Schema](https://github.com/user-attachments/assets/a5bcd2fd-df18-42cf-bdcf-36b27b485fb8)

Created tables and imported CSV files into their respective tables.

![Database Schema](https://github.com/user-attachments/assets/66f42f2a-b5b8-49f4-a133-99a0d9281097)

![Database Schema](https://github.com/user-attachments/assets/c6d941fc-455e-4506-8dac-c9ddec2474ef)

We were mindful about the order in which the tables has to be created in PgAdmin to ensure that the data was properly imported. Since the campaign table takes foreign keys from category, subcategories and contact tables, We created this table last.

Used **Select** statements to confirm data import.

![select statments](https://github.com/user-attachments/assets/fe4a3dd2-4d11-4ed0-b57b-60e3dd029e66)

## Technologies Used:
1. Python
2. PostgreSQL
3. Jupyter Notebook
4. QuickDBD (for ERD design)

## Conclusion:
In order to complete ETL mini project there were certain steps involved which ranges from extracting raw data to loading it into a relational database. Also, creating a database which supports efficient querying of crowdfunding campaigns, categories, subcategories, and contact details.
