# Customer Churn Analysis


## Problem Statement:
The goal of this project is to analyze customer churn, which is the rate at which customers leave a business relative to the total customers. By studying the churn rate against various factors, we aim to identify the main contributors to churn and provide actionable insights for business users. These insights will help businesses strategize and make informed decisions to reduce churn.

## Dataset

The data for this project is a CSV file containing the following columns:

### Column	Description
- customer_id = Unique identifier for each customer

- credit_score = Credit score of the customer

- country = Country of the customer

- gender = Gender of the customer

- age =	Age of the customer

- tenure Duration (in years) = the customer has been with the company

- balance = Account balance of the customer

- products_number =	Number of products owned by the customer

- credit_card = Whether the customer owns a credit card (1 = Yes, 0 = No)

- active_member = Whether the customer is an active member (1 = Active, 0 = Inactive)

- estimated_salary = Estimated salary of the customer

- churn =  Whether the customer churned (1 = Yes, 0 = No)


## Data Collection and Preparation

### 1. Connect, Clean, and Transform Data:

1. Imported the dataset into Power Query.
2. Promoted the first row as headers.
3. Removed unnecessary columns (e.g., estimated_salary).
4. Renamed steps and columns for clarity.
5. Checked and updated data types.
6. Replaced binary values with meaningful labels:
7. Credit card: 1 → Owned, 0 → Not Owned.
8. Activity status: 1 → Active, 0 → Inactive.
9. Churn status: 1 → Churned, 0 → Not Churned.

### 2. Created Conditional Columns:

1. Age Group: Categorized ages into groups.
2. Credit Score Category: Classified credit scores.
3. Account Balance Category: Grouped balances.


## Data Modeling

### 1. Reference Tables:

1. Created a reference table for Age Group containing distinct values.
2. Created a reference query for Account Balance and removed duplicates.
3. Created a reference query for Credit Score and removed duplicates.

### 2.Created Measures:

1. Customers = COUNT('Bank Customer Data'[Customer ID])
2. Customers Lost = CALCULATE(COUNT('Bank Customer Data'[Churn Status]), 'Bank Customer Data'[Churn Status] = "Churned")
3. Churn Rate = 'Bank Customer Data'[Customers Lost] / 'Bank Customer Data'[Customers]


## Visualizations
#### 1. Donut Charts:

- Customers by activity status, credit card status, country, and product ownership.

#### 2. Line and Clustered Column Charts:

- Customers by age group vs. churn rate.
- Customers by credit score vs. churn rate.
- Customers by account balance vs. churn rate.

#### 3. Slicers:

- Added slicers for filtering churn status.

#### 4. Gauge Chart:

- Showed churn rate with maximum, minimum, and target rates.

#### 5. card:

- Show Total Customers.



## Insights and Findings


###  Behavioral Insights

1. Age Groups:
- Major Segment: Customers aged 41-50 form the largest group but have the highest churn rates.
- Lower Churn Groups: Younger customers (21-30) and older customers (61+) are less likely to churn.

2. Credit Scores:
- High-Risk Segment: Customers with credit scores below 600 are most likely to churn.
- Low-Risk Segment: Customers with scores above 800 exhibit the lowest churn rates.

3. Account Balance:
- High Churn Range: Customers with account balances between 100K-200K churn the most.
- Low Churn Range: Balances below 10K or above 200K have significantly lower churn.

