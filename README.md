# Amazon_Sales

1. Problem Statement:
Amazon’s sales data is vast and complex, making it challenging to derive actionable insights. The lack of a centralized visualization system hinders decision-making. Key challenges include:
•	Tracking sales performance across years, regions, markets, and customer segments.
•	Analyzing production units, quantities, and return rates. 
•	Measuring profitability by customer and segment. 
•	Managing data integration, refresh, and access control.

2. Objective:
Develop a Power BI dashboard to: 
•	Visualize KPIs: Yearly sales, regional sales, production units, sales vs. production, returns by segment, market performance, and customer profitability. 
•	Enable automated data refresh. 
•	Provide role-based access to stakeholders.

4. Technology Used:
•	Power BI: Dashboard creation & visualization. 
•	Power Query: Data transformation. 
•	DAX: Measures for KPIs. 
•	Excel: Initial data cleaning. 
•	SharePoint/SQL Server: Centralized data storage. 
•	Power BI Gateway: Scheduled data refresh.

6. Scope of the Project:
•	Data integration from Excel, SQL, and cloud sources. 
•	Interactive dashboards for 8+ KPIs. 
•	Scheduled refresh and access control.

8. Requirement Gathering:
•	KPIs: Yearly Sales Trend | Sales by Region | Sales vs. Production Units | Return Rates by Segment | Profit by Customer. 
•	Data Sources: Sales transactions, returns, customer metadata. 
•	User Needs: Real-time dashboards, export options, role-based access.

9. Model Development:
Tables:
•	Fact: Sales (OrderID, Quantity, Revenue), Returns (ReturnID, Reason). 
•	Dimension: Time, Product, Customer, Region. 
Relationships: Star schema linking Sales to all dimensions. 
Data Cleaning: Removed duplicates, standardized regions, handled nulls.

11. DAX Queries and Execution Results:
•	Total Sales = SUM (Sales [Revenue])  
{This query shows total sales}
•	Regional Sales = SUMX(RELATEDTABLE(Sales), Sales [Revenue])  
{This query shows sales by region}
•	Customer Profit = CALCULATE ([Total Sales] - [Total Cost], FILTER (Customer, Customer [Segment] = "Prime"))  
{This query shows profit by customer}

13. Data Refresh & Schedule Refresh:
•	Manual Refresh: Directly via Power BI Desktop. 
•	Scheduled Refresh: Daily refresh using Power BI Gateway (for on-premises SQL data).

15. Publish Report & Access Control:
•	Published to Power BI Service workspace. 
•	Shared with stakeholders via link/email. 
•	Row-Level Security: Restricted region-specific data for regional managers.

17. Challenges Faced:
•	Data Volume: Slowed down queries; optimized by aggregating tables. 
•	DAX Complexity: Debugged using Performance Analyzer. 
•	Inconsistent Region Labels: Standardized using Power Query.

19. Future Improvements:
•	Integrate real-time sales APIs. 
•	Add AI-driven forecasting. 
•	Mobile-friendly dashboard design.

21. Conclusions:
The Power BI dashboard successfully tracks Amazon’s sales KPIs, enabling data-driven decisions. Automated refresh and access controls ensure scalability and security.





