Hello everyone!
I'm excited to share my project about analyzing credit card transactions and customer reports using a tool called Power BI.
Here's what I've been working on:
Project Objective: I created a weekly dashboard report that shows important information about how our credit card operations are doing. This report helps people who need to make decisions about credit cards to see what's going on in real-time.

Tools Used:
Microsoft Power BI: This is the main tool I used to make the report.
Data sources: I got information from two places: a database called MySQL and Excel files.
How I Got the Data: I used SQL to get the data from the database. This makes sure that the report always has the latest information without needing someone to update it manually.

What I Did with the Data: I used something called DAX queries to analyze the data and calculate things like weekly trends and important numbers.

DAX Queries :-
AgeGroup = SWITCH( TRUE(),
'public cust_detail'[customer_age] < 30, "20-30", 'public cust_detail'[customer_age] >= 30 && 'public cust_detail'[customer_age] < 40, "30-40", 'public cust_detail'[customer_age] >= 40 && 'public cust_detail'[customer_age] < 50, "40-50", 'public cust_detail'[customer_age] >= 50 && 'public cust_detail'[customer_age] < 60, "50-60", 'public cust_detail'[customer_age] >= 60, "60+", "unknown" )

IncomeGroup = SWITCH( TRUE(),
'public cust_detail'[income] < 35000, "Low", 'public cust_detail'[income] >= 35000 && 'public cust_detail'[income] <70000, "Med", 'public cust_detail'[income] >= 70000, "High", "unknown"
week_num2 = WEEKNUM('public cc_detail'[week_start_date])
Revenue = 'public cc_detail'[annual_fees] + 'public cc_detail'[total_trans_amt] + 'public cc_detail'[interest_earned]

Current_week_Reveneue = CALCULATE( SUM('public cc_detail'[Revenue]), FILTER( ALL('public cc_detail'), 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])))
Previous_week_Reveneue = CALCULATE( SUM('public cc_detail'[Revenue]), FILTER( ALL('public cc_detail'), 'public cc_detail'[week_num2] = MAX('public cc_detail'[week_num2])-1)

Dashboard Features: The report has two main parts:
Credit Card Transaction Report: This part shows details about transactions, like how much money we made, what kind of jobs people have, whether they used a chip card, and trends over the weeks.
Credit Card Customer Report: Here, you can see information about our customers, like how much money they spend based on their gender, job, education, and more. It also shows how much it costs to get new customers and how much money they spend in total.
The report is easy to use and has buttons and graphs that you can interact with to explore the data better.

I worked hard to make sure this report helps people make better decisions using data. I hope it helps us understand our credit card operations better! Let me know if you have any questions or need more information.


