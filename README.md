# H1B Visa Dashboard

This project involves analyzing the H1B visa dataset and creating an interactive Power BI dashboard to visualize key insights on the data. The dataset covers visa applications filed from 2020 to 2024 and includes a variety of metrics such as case status, visa class, job titles, and employer information.

## Overview

The goal of this project is to explore, clean, and visualize the H1B visa dataset for the purpose of understanding trends in visa distribution, job categories, approval rates, and other relevant factors.

## Key Visualizations

The Power BI dashboard displays the following insights:

- **Visa Class Distribution**: Breakdown of visa types (H-1B, E-3, etc.) and their respective approval rates.
- **Count of CASE_STATUS**: The number of applications based on their case status (e.g., Certified, Denied, Withdrawn).
- **Employee City Distribution**: Visualization of employee city locations.
- **Top Job Titles**: A visualization of the distribution of job titles across different case statuses.
- **Monthly Visa Distribution**: A month-wise distribution of visa approvals and denials.
- **Worksite and Employer Information**: Details on employers, including the top companies sponsoring H1B visas.
- **Field of Jobs Based on Approval**: A breakdown of job titles based on visa approval.

## Dataset Description

The H1B visa dataset includes data on thousands of visa applications, such as:

- **CASE_NUMBER**: Unique identifier for each application.
- **CASE_STATUS**: The status of the visa application (e.g., Certified, Denied).
- **VISA_CLASS**: The type of visa (e.g., H-1B, E-3).
- **JOB_TITLE**: The job title for the visa applicant.
- **EMPLOYER_NAME**: The employer sponsoring the visa application.
- **WORKSITE_CITY**: The city where the applicant will work.
- **WORKSITE_STATE**: The state where the applicant will work.
- **WAGE_RATE_OF_PAY_FROM**: The salary offered to the applicant.
- **WAGE_RATE_OF_PAY_TO**: The upper bound of the offered salary.
- **MONTHLY DISTRIBUTION**: Number of applications processed per month.

The dataset contains four CSV files from 2020 to 2024, which were uploaded to Azure Blob Storage. After uploading, the files were combined into a single CSV file and cleaned by performing the following operations:

- **Removing null values**: Columns with more than 40% null values were dropped.
- **Handling missing data**: Null values were replaced with appropriate defaults or dropped as necessary.

## Data Cleaning

The following cleaning steps were performed on the dataset:

1. **Removing columns with over 40% null values**: Columns such as `EMPLOYER_ADDRESS1`, `EMPLOYER_PHONE`, and others with too many missing values were removed.
2. **Replacing null values**: Columns that had significant but manageable missing data were imputed with default values (e.g., "Unknown" for missing employer names).
3. **Standardization**: Columns such as `VISA_CLASS`, `JOB_TITLE`, and `CASE_STATUS` were standardized to ensure consistency in naming conventions.
4. **Date Formatting**: Columns like `RECEIVED_DATE`, `DECISION_DATE`, and `ORIGINAL_CERT_DATE` were formatted into a consistent date format.

## Technical Details

- **Power BI Desktop** was used to create the dashboard.
- **Data Processing**: The dataset was cleaned and transformed using Python (pandas, numpy).
- **Data Storage**: The data was uploaded to **Azure Blob Storage** for easy access and processing.

## Project Structure

```bash
|-- data/
|   |-- h1b_data_2020.csv
|   |-- h1b_data_2021.csv
|   |-- h1b_data_2022.csv
|   |-- h1b_data_2023.csv
|   |-- h1b_data_2024.csv
|   |-- cleaned_h1b_data.csv  # Final combined and cleaned dataset
|
|-- dashboard/
|   |-- h1b_dashboard.pbix  # Power BI file for the dashboard

|-- README.md  # This file
