# Credit Card Financial Dashboard
### About this Project
#### Credit Card Transaction and Customer Report [Power BI | SQL]
+ Developed an interactive dashboard using transaction and customer data from SQL database.
+ Data Preprocessing & analysis to monitor key performance metrices & trends.
+ Shared actionable insights with stakeholders based on dashboard finding to support decision making process.

#### Import data to SQL database
1. Prepare csv file
2. Create tables in SQL
3. import csv file into SQL

#### DAX Queries used
1) IncomeGroup = SWITCH(
               TRUE(),
               'customer (2)'[Income] < 35000, "Low",
               'customer (2)'[Income] >= 35000 && 'customer (2)'[Income] <70000, "Med",
               'customer (2)'[Income] >= 70000, "High",
                "unknown"
)

2) AgeGroup = SWITCH(
TRUE(),
'customer (2)'[Customer_Age] < 30, "20-30",
'customer (2)'[Customer_Age] >= 30 && 'customer (2)'[Customer_Age] < 40, "30-40",
'customer (2)'[Customer_Age] >= 40 && 'customer (2)'[Customer_Age] < 50, "40-50",
'customer (2)'[Customer_Age] >= 50 && 'customer (2)'[Customer_Age] < 60, "50-60",
'customer (2)'[Customer_Age] >= 60, "60+",
"unknown"
)

3) week_num2 = WEEKNUM('credit_card (1)'[Week_Start_Date])

4) Revenue = 'credit_card (1)'[Annual_Fees] + 'credit_card (1)'[Total_Trans_Amt] + 'credit_card (1)'[Interest_Earned]

5) Previous_week_Reveneue = CALCULATE(
SUM('credit_card (1)'[Revenue]),
FILTER(
ALL('credit_card (1)'),
'credit_card (1)'[week_num2] = MAX('credit_card (1)'[week_num2])-1))

6) Current_week_Reveneue = CALCULATE(
SUM('credit_card (1)'[Revenue]),
FILTER(
ALL('credit_card (1)'),
'credit_card (1)'[week_num2] = MAX('credit_card (1)'[week_num2])))
