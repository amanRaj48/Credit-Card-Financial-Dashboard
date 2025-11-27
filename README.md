# Credit-Card-Financial-Dashboard
Credit Card Financial Dashboard built using Power BI to analyze spending behavior, income groups, customer segmentation, and transaction trends with interactive visuals and DAX measures.


💡 Credit Card Transaction Dashboard – Power BI Workflow



1. Data Import & Modeling

Imported data using Text/CSV mode.

-Loaded two tables: credit_card, customer.

2.Calculated Column

-Week_Num2 = WEEKNUM(credit_card[Week_Start_Date])

3. Measures Created(DAX Query)

a.)Current_Week_Revenue = 

CALCULATE(

  SUM(credit_card[Revenue]),

  FILTER(

    ALL(credit_card),

    credit_card[Week_Num2] = MAX(credit_card[Week_Num2])

  )

)

b.)Previous_Week_Revenue = 

CALCULATE(

  SUM(credit_card[Revenue]),

  FILTER(

    ALL(credit_card),

    credit_card[Week_Num2] = MAX(credit_card[Week_Num2]) - 1

  )

)

c.)WOW_Revenue = 

DIVIDE(

  [Current_Week_Revenue] - [Previous_Week_Revenue],

  [Previous_Week_Revenue]

)  , where WOW_Revenue is week over week revenue.

4. Income Group Classification

-IncomeGroup = 

SWITCH(

  TRUE(),

  customer[Income] < 35000, "Low",

  customer[Income] >= 35000 && customer[Income] < 70000, "Medium",

  customer[Income] >= 70000, "High",

  "Unknown"

)



5. Visuals Used in the Dashboard



a.) 1 Line & Stacked Column Chart(Qtr Revenue vs Total Transaction Count).

b.) 5 Stacked Bar Charts(Revenue by Expenditure Type,Revenue by Job Type,Revenue by Education Level,Revenue by Card Type,

Revenue by Card Utilisation Mode).

c.) 1 Table(columns naming:Card Category,Sum of Revenue,Sum of Transaction Amount,Sum of Interest Earned).

d.) 4 Treemaps (Quarter,Card Category,Income Group,Gender).

e.)1 Slicer(Week Start Date Filter).

f.) 4 KPI Cards(Sum of Revenue,Interest Earned,Total Transaction Amount,Total Transaction Count).

Dashboard Images : 1. <img width="1362" height="761" alt="CC_Transaction_Report" src="https://github.com/user-attachments/assets/83e5d387-e07d-4d6d-a18c-31cd93bcfd10" />

                   2. <img width="1400" height="755" alt="CC_Customer_Report" src="https://github.com/user-attachments/assets/2d521d83-a22e-4f5a-8d53-bdead6439b0b" />


6. Key Learning Outcomes

-Time intelligence using weekly comparisons.

-Multi-dimensional revenue analysis.



Feel free to connect with me on LinkedIn: https://www.linkedin.com/in/aman-raj46983/

#PowerBI #DataAnalytics #DashboardDesign #BusinessIntelligence #DataAnalystJourney #DAX #DataVisualization #LearningByDoing #AnalyticsProject

