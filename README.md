Amazon India Sales Report – DADM Group Project

E-commerce Decision Modeling: Amazon India Sales

Course: Data Analytics and Decision Making (DADM)
Team Members: Pavan, Kambam, Lawan, Aaron, Arush, Aerio
Content Freeze: 7 November 2026
Submission Deadline: 10 November 2026

---

1. Project Overview

This project analyses an Amazon India Sales dataset to explore e-commerce business performance and support data-driven decision-making.

The project applies several analytical techniques taught in the DADM course, including:

- Multiple Linear Regression
- Logistic Regression
- Classification Decision Trees
- K-means and Hierarchical Clustering
- Short-term Time-Series Forecasting

The objective is to identify meaningful patterns, evaluate predictive models, understand cancellation risks, discover product/market segments, and forecast short-term sales or demand.

2. Dataset Information

Attribute| Description
Dataset Name| Amazon Sales Report
Source| Kaggle – mdsazzatsardar
Observation Unit| Individual order line items (SKUs)
Total Observations| 128,975
Total Columns| 22
Date Range| 31 March 2022 – 29 June 2022
Unique Order IDs| 120,378
Unique SKUs| 7,195

Important: The dataset contains approximately four months of observations. Annual seasonality cannot reliably be inferred.

3. Software and Technologies

- R (Version 4.0 or higher recommended)
- Google Colab (for cloud-based execution)
- RStudio (optional local development environment)

R Packages

- "dplyr" – Data manipulation
- "ggplot2" – Data visualization
- "lubridate" – Date handling
- "rpart" – Classification trees
- "forecast" – Time-series forecasting

Additional packages should be documented in the relevant analysis scripts.

4. Repository Structure

Amazon_India_Sales_DADM/
│
├── Amazon Sale Report.csv
├── data_preparation.R
├── Cleaned_Analysis_Dataset.csv
├── Data_Dictionary.xlsx
├── Team_Project_Brief.docx
├── Data_Audit_Report.pdf
├── README.md
│
├── EDA/
│   └── EDA_Charts/
│
├── Analysis/
│   ├── Pavan_Regression/
│   ├── Kambam_Logistic_Regression/
│   ├── Lawan_Decision_Tree/
│   ├── Aaron_Clustering/
│   └── Arush_Forecasting/
│
└── Final_Report.pdf

5. File Descriptions

File| Purpose
"Amazon Sale Report.csv"| Original, unmodified raw dataset
"data_preparation.R"| Reproducible data-cleaning pipeline
"Cleaned_Analysis_Dataset.csv"| Shared dataset used for analysis
"Data_Dictionary.xlsx"| Column definitions and cleaning documentation
"Team_Project_Brief.docx"| Agreed project definitions and modelling guidelines
"Data_Audit_Report.pdf"| Data quality and audit findings
"EDA/"| Exploratory data analysis charts
"Analysis/"| Individual members' analysis scripts and results
"Final_Report.pdf"| Integrated group project report

6. How to Execute the Data Preparation Pipeline

Step 1: Obtain the raw dataset

Download the original Amazon Sale Report CSV from the Kaggle source and place it in the project root directory.

Step 2: Install required packages

install.packages(c(
  "dplyr",
  "ggplot2",
  "lubridate"
))

Step 3: Set the working directory

setwd("path/to/Amazon_India_Sales_DADM")

Step 4: Execute the preparation script

source("data_preparation.R")

Step 5: Verify the output

Confirm that "Cleaned_Analysis_Dataset.csv" has been generated and that its dimensions and cleaning results match the documented dataset version.

7. Data Cleaning and Preparation Decisions

The preparation pipeline includes:

1. Removal of unnecessary export artifact columns ("index" and "Unnamed..22").
2. Standardization of blank character strings into proper "NA" values.
3. Identification and examination of duplicate records.
4. Retention of missing Amount and zero-Quantity observations for analyses where they are relevant.
5. Preservation of the original raw dataset.

Important Data Quality Decisions

- Missing Amount: 7,795 observations are retained in the shared dataset. Regression modelling must explicitly handle missing Amount values.
- Missing Courier.Status: 6,872 observations. This variable is excluded from predictive cancellation models due to post-outcome information leakage.
- Missing fulfilled.by: 89,698 observations.
- Missing promotion.ids: 49,153 observations.
- Exact duplicates: Six exact duplicate rows are retained pending justification for any removal.

8. Analytical Workstreams

Team Member| Analytical Workstream| Technique
Pavan| Order Value Modelling| Linear Regression
Kambam| Cancellation Risk Prediction| Logistic Regression
Lawan| Cancellation Classification| Decision Tree
Aaron| Product/Market Segmentation| Clustering
Arush| Daily Demand Forecasting| Time-Series Methods
Aerio| Data Preparation and Integration| Data Auditing and EDA

9. Important Modelling Guidelines

- Regression analysis must explicitly handle missing Amount and zero-Quantity observations.
- Logistic regression and decision tree classification must use the same cancellation target, eligible predictors and train/test observations.
- "Courier.Status" must not be used as a predictive classification variable.
- Customer-level segmentation must not be claimed because a verified customer identifier is unavailable.
- Forecasting must use chronological training and testing periods rather than random splitting.
- Annual seasonality must not be claimed because of the short observation period.
- All analytical results must be supported by actual executed code.

10. Exploratory Data Analysis

The initial EDA includes:

- Order status distribution.
- Product category breakdown.
- Top shipping states.
- Quantity distribution.
- Daily line-item trends.

These visualizations help identify patterns and provide context for subsequent analytical modelling.

11. Project Reproducibility

All data preparation and analytical procedures should be supported by executable R scripts.

The original dataset is preserved separately from the cleaned dataset. Cleaning decisions, modelling assumptions, exclusions and transformations must be documented.

All reported statistics, graphs, evaluation metrics and conclusions should be traceable to the corresponding analysis scripts and outputs.

12. Limitations

- The dataset covers approximately four months.
- No verified customer identifier is available for customer-level segmentation.
- Several columns contain substantial missing data.
- Shipping progress information may contain post-outcome leakage.
- Historical patterns may not necessarily represent future e-commerce performance.

13. Project Submission

Submission Format: PDF
Submission Platform: Moodle
Submission Deadline: 10 November 2026

Only one final integrated report should be submitted per group.

---

Prepared for: Data Analytics and Decision Making (DADM)
Project: Amazon India Sales Report
Academic Year: 2026
