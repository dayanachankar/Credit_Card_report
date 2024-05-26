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
IncomeGroup = SWITCH(
               TRUE(),
               'customer (2)'[Income] < 35000, "Low",
               'customer (2)'[Income] >= 35000 && 'customer (2)'[Income] <70000, "Med",
               'customer (2)'[Income] >= 70000, "High",
                "unknown"
)
