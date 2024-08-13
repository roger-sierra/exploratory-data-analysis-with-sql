# Exploratory Data Analysis with SQL

## Overview

This repository contains a SQL script designed to perform Exploratory Data Analysis (EDA) on a dataset containing information about company layoffs. The script includes various analytical queries that summarize key insights such as total layoffs, industry impacts, trends over time, and more.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Prerequisites](#prerequisites)
- [Script Details](#script-details)
- [Usage](#usage)

## Dataset

The script is designed to work with a dataset of company layoffs, which includes information such as the company name, industry, total laid off, percentage laid off, date, stage, and funds raised. The dataset should be imported into a MySQL database table called `layoffs_staging2`.

## Prerequisites

Before running the script, ensure you have the following:

- **MySQL**: The script is written for MySQL, so you need a MySQL server set up on your machine or a remote server.
- **Database Setup**: A database with the `layoffs_staging2` table containing your data.

### Sample Table Structure

Here's a basic structure of the `layoffs_staging2` table:

```sql
CREATE TABLE `layoffs_staging2` (
  `company` text,
  `industry` text,
  `total_laid_off` int DEFAULT NULL,
  `percentage_laid_off` float DEFAULT NULL,
  `date` date DEFAULT NULL,
  `stage` text,
  `funds_raised_millions` int DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

## Script Details

The SQL script performs the following analytical steps:

1. **Data Overview**:
   - Retrieves all records from the `layoffs_staging2` table for an initial exploration of the dataset.

2. **Key Metrics Calculation**:
   - Calculates maximum values for `total_laid_off` and `percentage_laid_off`.
   - Identifies companies with 100% layoffs and orders them by `total_laid_off` and `funds_raised_millions`.
   - Aggregates total layoffs by `company`, `industry`, and `stage`.

3. **Time-Based Analysis**:
   - Retrieves the date range of the layoffs.
   - Aggregates layoffs by year, month, and calculates rolling totals.

4. **Top Companies Analysis**:
   - Identifies the top companies by layoffs each year using a ranking system.

## Usage

1. **Import Data**:
   - Import your dataset into the `layoffs_staging2` table in your MySQL database.

2. **Run the Script**:
   - Execute the SQL script to conduct the exploratory data analysis and generate insights.

3. **View Results**:
   - Query the `layoffs_staging2` table or any temporary tables created during the analysis to view the results.
   - Export the results if needed for further visualization or reporting.


