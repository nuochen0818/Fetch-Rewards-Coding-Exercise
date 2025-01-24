# Fetch Rewards Coding Exercise - Analytics Engineer

## 1. Overview

I am using SQLite for this exercise. This exercise can demonstrate how I reason about data and how I communicate your understanding of a specific data set to others.

## 2. How to run

### 2.1 Setup

Ensure some important python packages are installed on your system.

> pandas, sqlite3, datetime, json

### 2.2 Running the Code

The python code could run directly if system environment is done. Should be careful when setting the file path.



## 3. How it works

### STEP1: Review Existing Unstructured Data and Diagram a New Structured Relational Data Model

I designed the ER diagram here (https://dbdiagram.io/d/Fetch-data-model-6791c10037f5d6cbeba3bc62), which includes five tables representing information about users, receipts, brands, receipt_items, and cpgs separately. 
<img width="699" alt="Screen Shot 2025-01-24 at 10 44 48 AM" src="https://github.com/user-attachments/assets/2c5c2f21-2148-497a-8211-0b1bdfbb77c6" />

Then, I created the tables based on the ER diagram and loaded the data into them for further analysis.

### STEP2: Write queries that directly answer predetermined questions from a business stakeholder

I choosed to answer question 3 and 4.

### STEP3: Evaluate Data Quality Issues in the Data Provided

I used Python and SQL to evaluate the data quality issues in the provided dataset, focusing on three main aspects: missing values, duplicates, abnormal values, and invalid values. Additionally, I performed exploratory data analysis from a statistical perspective.

### STEP4: Communicate with Stakeholders

Hi, I’ve been analyzing the data we’re working with for the project, and I’d like to share some findings and questions related to data quality, along with proposed next steps.  

#### Key Observations  
1. **Data Quality Issues**:  
   - A significant number of missing values were identified, particularly in critical fields like `date_scanned` and product descriptions like `barcode`. Missing dates make it difficult to track when receipts were processed, as well as to link the tables together. This can impact downstream reporting.  
   - Inconsistent entries, such as non-standardized product `descriptions` and `bonus points earned reasons`, were also observed.

2. **Discovery Process**:  
   - These issues were uncovered using exploratory data analysis, including checks for missing values and statistic analysis.  

#### Questions and Information Needed   
- What are the acceptable thresholds for missing or invalid data? If we keep all the data with invaild valuses for importnt variables (like `date_scanned`), can we try imputation?  
- Are there documented we can use to validate key fields for products like `item_price` or fill in the product descriptions by ourselves?   

#### Additional Context for Optimization   
- Feedback from stakeholders on which dimensions of the data are most critical
- A clear understanding of how this data will be used. If it is for reporting or decision making, who would be the audiences? 
- Access to data dictionary that outlines the expected format, constraints, and the business meaning for each field.  

#### Anticipated Production Challenges  
- **Performance**: Large datasets with complex joins or aggregations could slow down queries.   
- **Scaling**: As data volume grows, we need to ensure our infrastructure can handle increased storage and compute requirements. Leveraging cloud-based solutions with auto-scaling capabilities would help mitigate this.  
- **Data Integrity**: Automated data quality checks should be implemented to catch issues early. Tools like data pipelines with validation steps can be useful here.  

#### Next Steps   
- Implement a plan to clean, standardize, and validate critical fields in the dataset.  
- Set up automated monitoring and alerts to flag future data quality issues.  
