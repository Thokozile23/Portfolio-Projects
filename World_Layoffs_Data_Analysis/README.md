# World Layoffs Data 📉🌍

## Overview 🔍

This project analyzes the **World Layoffs** dataset, sourced from [Kaggle](https://www.kaggle.com) and combined into one CSV file on my GitHub repository: [layoffs.csv](https://github.com/Thokozile23/Portfolio-Projects/blob/6e07a9fbf155c74efcb637bda17f58220924d796/layoffs.csv). The dataset covers mass layoffs across multiple countries from **March 11, 2020**, to **March 6, 2023**, capturing data on **companies**, **layoff dates**, **industries**, and **percentage of workforce affected**. This analysis explores the impact of layoffs during the **COVID-19 pandemic**.

---

## Data Cleaning Process 🧹

### 1. **Removing Duplicates** 🔄
- Created a **layoffs_staging** table to preserve raw data.
- Used row numbers to identify and remove duplicate records.
- Eliminated duplicates from the dataset using a second table, **layoffs_staging2**.

### 2. **Standardizing Data** 📏
- Removed leading/trailing spaces in the **company** field.
- Standardized company names starting with "Crypto" to **Crypto**.
- Corrected entries in the **country** field, removing trailing periods (e.g., "United States.").
- Converted the **date** column from string format to **MySQL DATE** format.

### 3. **Handling Null or Blank Values** 🚫
- Replaced empty **industry** fields with **NULL**.
- Matched NULL industry records with other entries based on company and location to fill in missing values.

### 4. **Removing Irrelevant Records and Columns** 🗑️
- Removed records with NULL values for **total_laid_off** and **percentage_laid_off**.
- Dropped the **row_num** column used for duplicate identification.

---

## Exploratory Data Analysis (EDA) 📊

### Key Insights and Findings 🔑

- **Highest Layoff Count**: **12,000** in a single instance.
- **Maximum Layoff Percentage**: **100%** of workforce laid off in some cases.

### 1. **Company Analysis** 🏢
- **Most Affected Company**: **Amazon** with a total of **18,150** layoffs.
- **Yearly Leaders**: 
  - **2023**: **Google** with **12,000** layoffs.
  - **2022**: **Meta** with **11,000** layoffs.

### 2. **Industry Trends** 📉
- **Most Affected Industry**: **Consumer sector** with **45,182** layoffs.

### 3. **Geographic Trends** 🌍
- **Countries with Most Layoffs**:
  - **United States**: **256,420** layoffs.
  - **India**: **35,793** layoffs.

### 4. **Yearly Trends** 📅
- **2020**: **80,998** layoffs.
- **2023**: **125,677** layoffs, a significant increase.

### 5. **Company Stages** 📊
- **Most Affected Stage**: **Post-IPO** companies with **204,073** layoffs.

### 6. **Monthly Trends** 📅
- **Peak Month**: **January 2023** with **84,714** layoffs.

### 7. **Cumulative Impact** 📈
- **Layoff totals** have increased progressively over the years, reflecting the broader economic impacts of the pandemic.

### 8. **Top Companies by Year** 🏆
- **2020**: **Uber**
- **2021**: **ByteDance**
- **2022**: **Meta**

---

## Conclusion 🎯

This project offers deep insights into **mass layoffs** across several countries and industries, focusing on the impact of **COVID-19** on workforce reductions. It explores key trends, including the **companies** most affected, **geographical distribution**, and the **industry** trends during the pandemic. The findings contribute to understanding the wider economic effects of the global crisis on businesses.

---

Feel free to explore the full dataset and analysis to uncover more insights on the effects of **mass layoffs** over the last three years. 📊💼

