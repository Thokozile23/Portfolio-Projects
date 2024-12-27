**World Layoffs Data**

**Overview**

This project analyzes a dataset called World Layoffs, sourced from kaggle and combined into one csv file in https://github.com/Thokozile23/Portfolio-Projects/blob/6e07a9fbf155c74efcb637bda17f58220924d796/layoffs.csv. The dataset focuses on mass layoffs in several countries between March 11, 2020, to March 6, 2023. It includes information about the country, companies, layoff dates, industries, and the percentage of workforce affected. This analysis explores how layoffs occured since the COVID-19 pandemic.

**Data Cleaning Process**
1. **Removing Duplicates**
To ensure data integrity, duplicates were removed systematically:
•	Created a new table, layoffs_staging, with the same structure as the original layoffs table to preserve the raw data.
•	Populated layoffs_staging with data from the original table.
•	Assigned a unique row number to each record within partitions defined by specified columns, identifying duplicates with row numbers greater than 1.
•	Created a second table, layoffs_staging2, which included the additional row_num column for duplicate identification.
•	Removed records with row_num > 1 in layoffs_staging2, effectively eliminating duplicates.

2. **Standardizing Data**
Several steps were taken to ensure consistency across the dataset:
•	Removed leading and trailing spaces in the company field.
•	Standardized entries starting with "Crypto" to a uniform Crypto.
•	Corrected entries in the country column by removing trailing periods for entries starting with "United States".
•	Converted the date column from string format to the MySQL DATE type using the STR_TO_DATE() function.
•	Altered the date column to ensure it adhered to the DATE format.

4. **Handling Null or Blank Values**
To address incomplete data:
•	Set empty values in the industry field to NULL.
•	Matched records with NULL or blank industry fields against other records to fill in missing values based on the same company and location. For example: 
o	Updated t1.industry with t2.industry where t1.industry is NULL and t2.industry is not NULL for matching companies.

5. **Removing Irrelevant Records and Columns**
To streamline the dataset:
•	Deleted records where both total_laid_off and percentage_laid_off were NULL, as they lacked essential information.
•	Dropped the row_num column, which was used only for duplicate identification.

**EXPLORATORY DATA ANALYSIS**

Key Insights and Findings

1.	**Layoff Statistics**
•	Highest Layoff Count: 12,000 in a single instance.
•	Maximum Layoff Percentage: 100% across all records.

2.	**Company Analysis**
•	Most Affected Company: Amazon with a total of 18,150 layoffs.
•	Yearly Leaders: Google (12,000 layoffs in 2023) and Meta (11,000 layoffs in 2022).

3.	**Industry Trends**
•	Most Affected Industry: Consumer sector with 45,182 layoffs.

4.	**Geographic Trends**
•	Countries with Most Layoffs: United States (256,420) and India (35,793).

5.	**Yearly Trends**
•	Layoffs increased from 80,998 in 2020 to 125,677 in 2023.

6.	**Company Stages**
•	Most Affected Stage: Post-IPO companies with 204,073 layoffs.

7.	**Monthly Trends**
•	Peak Month: January 2023 with 84,714 layoffs.

8.	**Cumulative Impact**
•	Layoff totals increased progressively over the years.

9.	**Top Companies by Year**
•	2020: Uber.
•	2021: ByteDance.
•	2022: Meta.



