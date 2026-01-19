# Retail-company-sales-analysis
Power BI | SQL | Google sheets

## Bowman Goods sales analysis 2023-2024

### Project Background
Bowman Goods is a retail company operating on the US market since 2000. The business utilises a bricks-and-mortar strategy with physical stores across 47 states and 108 cities. 
The company has shown steady performance over the years. Management is interested in gaining a deeper understanding of Bowman Goods’ current performance and identifying opportunities for the company’s growth. 
The analysis covers Bowman Goods’ sales data for 2023-2024. The aim is to uncover critical insights that could improve Bowman Goods’ commercial success.
Insights and recommendations are provided across the key areas. The following business questions guided the analysis:

Sales Trends:
- How did revenue/profit grow in 2023-2024?
- How did profit margin change in 2023-2024?
- Are there any noticeable seasonal patterns?

Product Level Performance:
- Which categories generate the most revenue?
- Which products or categories show the highest revenue/profit margin?
- What is the revenue contribution from the top products?

Customer Segments:
- How concentrated are sales among key customers?

Regional Comparisons:
- Which region contributes the most to total revenue?
- Which regions show the highest profitability?

Metrics used in the analysis: Revenue, Profit, Profit margin, Average revenue per customer, Number of orders.

### Data Structure & Instruments Used
#### Data Structure

For the analysis we used a clean [.csv flat file](https://github.com/annaksondzyk/Retail-company-sales-analysis/blob/main/product_sales_dataset_final.rar) with sales data for Bowman Goods for 2023-2024.

The  Bowman Goods’ sales database structure after normalisation and additional calculations as seen below consists of six tables:
- FactSales – transactional sales data (200,000 rows)
- DimDate – calendar table (used for time-based analysis)
- DimProduct – product details (product ID, product name, category, subcategory)
- DimRegion – mapping of cities to regions and states
- _Measures – calculated measures
- Customers_City_count_aggr_2024 - additional calculation for distribution of customers by the number of cities where they made purchases
<img width="917" height="491" alt="image" src="https://github.com/user-attachments/assets/ccca3909-5a15-4c48-9699-9e34a7f41b6c" />

#### Instruments Used
- Power BI – calculations and visualisations
- SQL (SQL Server Management Studio) – data normalisation, complex calculation, which required aggregation
- Google Sheets – supplementary calculations and percentage checks

#### Links
- [Power BI dashboard](https://github.com/annaksondzyk/Retail-company-sales-analysis/blob/main/Bowman%20Goods%20-%20Sales_dashboard.pbix) (download required)
- [Power BI supporting visualizations](https://github.com/annaksondzyk/Retail-company-sales-analysis/blob/main/Bowman%20Goods%20-%20Supporting_visualizations.pbix) (download required)
- [SQL requests](https://github.com/annaksondzyk/Retail-company-sales-analysis/blob/main/Bowman%20Goods%20-%20SQL%20requests.pdf)
- [Google Sheets supporting calculations](https://docs.google.com/spreadsheets/d/1SxVfv9tNbjUxuZI06ypBCQvXcpeyt7UxB2F5FEO-UpI/edit?gid=0#gid=0)

### Executive Summary
Bowman Goods sales analysis shows 1.27% growth in revenue and profit margin in 2024. Sales records show strong seasonality peaking in October - December and the lowest revenue in February. The biggest category in sales, Electronics, shows the lowest margin of 15.1% in 2024 (average is 22.16%). No changes in the assortment took place between 2023 and 2024. Top 10 products accounted for 42.8% revenue in 2024. The client base has remained stable in 2023-2024. The highest-performing region by sales, East, showed the lowest margin of 20.55% (average is 22.16%).

Bowman Goods can benefit from increasing and smoothing monthly revenue by expanding a product range, introducing non-seasonal products and focused marketing activities. Cross-selling of high profit margin products (Accessories) could help increase profit margin. Online presence of Bowman Goods might be considered.

### Insights Deep Dive
#### Sales Trends
- In 2024, both revenue and profit increased by 1.27% compared to 2023 (revenue: 71.7 mUSD vs 70.8 mUSD; profit: 15.9 mUSD vs 15.7 mUSD) with 100.1k orders (2023: 99.8k orders).  
- The profit margin remained stable at 22.1% (2024: 22.16%, 2023: 22.15%). 
- Monthly sales in 2023-2024 showed seasonality: highest sales in October-December with a peak in November (2024: 13.9 mUSD, 2023: 13.3 mUSD) with further drop reaching the lowest sales in February (2024: 2.9 mUSD, 2023: 2.7 mUSD). For the rest of the year sales are rather stable with a small increase in March and May.
<img width="580" height="351" alt="image" src="https://github.com/user-attachments/assets/f5a052d5-d658-41fe-931f-8581cacc9e28" />

#### Product Level Performance
- Categories which show the highest sales levels, Electronics, Home & Furniture, show lower profit margins (15–24%). The category with the lowest revenue, Accessories, shows the highest margins (around 34%). 
- Accessories is also the only category that showed a slight decline in 2024 (-0.19 mUSD revenue, -0.07% profit margin).
<img width="836" height="260" alt="image" src="https://github.com/user-attachments/assets/bf652822-9d88-46d9-a917-e12c128c06f5" />

- No changes in the assortment between 2023 and 2024. The company sold 49 products in 4 categories. The category with the highest margin, Accessories, has the lowest assortment, 9 items. The category with the lowest margin, Electronics, has the largest - 16 items.
<img width="445" height="244" alt="image" src="https://github.com/user-attachments/assets/227d4246-3017-4893-a077-0ac7e5f0857d" />

- Top 10 products by revenue represent 20% of all SKUs and generated 42.8% revenue and 34.5% profit in 2024. They were composed of Electronics and Home & Furniture categories. 
- Top 10 products by profit included 3 additional Clothing & Apparel products replacing 3 Electronics products. Top 10 products by profit accounted for 37.5% profit in 2024. 
<img width="1012" height="273" alt="image" src="https://github.com/user-attachments/assets/a62b6cf0-38f5-44d6-a58e-8043f576390d" />

- Lists of top 10 products defined by both revenue and profit remained stable in 2023-2024.
- Top products sold by the company by both revenue and profit are Tempor-Pedic Mattress (Home & Furniture) and Instant Pot (Electronics). 
<img width="709" height="526" alt="image" src="https://github.com/user-attachments/assets/2d523636-04f3-45fd-a638-16e8f5f1b766" />

#### Customer Segments
- Customer analysis should be interpreted with caution, as identification is based on names rather than unique IDs. 
- Customer identification in the dataset is based on first and last name rather than unique ID, which may impact accuracy of the analysis. The following analysis is made based on the available data.
- Bowman Goods’ client base has remained stable with a 0.3% increase in 2024 compared to 2023 (2024: 71.2k unique customers, 2023: 71k unique customers).
- Average revenue per customer increased by approximately 1% (2024: 1,006 USD, 2023: 997 USD).
- Concentration of sales in top 10 customers is below 0.4% in both years (2024: 0.37%, 2023: 0.36%).
- 20.8% of clients visited shops located in more than 1 city in 2024.
<img width="477" height="307" alt="image" src="https://github.com/user-attachments/assets/7e385754-0f76-4b2a-a615-43fb86818a1a" />

#### Regional Comparisons
- Bowman Goods sells goods in physical shops across the US, being represented in 47 states and 108 cities during 2023-2024.
<img width="757" height="492" alt="image" src="https://github.com/user-attachments/assets/7e007aaa-e0f6-4550-bac4-882348316eec" />

- In 2024, the highest performing region for Bowman Goods is East, being first at customer count, share of revenue and profit, but with the lowest profit margin below Bowman Goods’ average at 20.55%. This is due to 54.9% of the region's sales coming from Electronics, the category with the lowest profit margin. 
Other regions show lower concentration on Electronics and more balanced sales structure, which also results in higher profit margins.
In 2024, the lowest performing region is South based on customer count, share of revenue and profit, however showing the highest profit margin among regions of 23.56%. 
<img width="768" height="491" alt="image" src="https://github.com/user-attachments/assets/997880ec-d4c3-40ad-8bf2-ab1349d0cd48" />

- The lowest level of data on location in the dataset is city. Information on separate shops is not included. Such information would provide for a more nuanced analysis.

### Recommendations
#### Sales Trends
- Increase sales in low-season months: Focus marketing activities, potentially on:
February - lowest sales during the year, try to benefit from a seasonal holiday (St.Valentine’s Day offerings)
March, May - a slight increase identified in both 2023 and 2024. Need to analyse the reason for increase and try to maximise it
- Consider feasibility of launching an online sales channel: Conduct a market research and benchmark analysis
#### Product Level Performance
- Expand the assortment: across all the categories with a particular focus on goods with higher profit margin (Accessories category) and non-seasonal products, which could increase and stabilise monthly revenue.
- Increase profit margin for lower margin product categories (Electronics, Home & Furniture): Negotiate with suppliers to decrease purchase cost, conduct search for new suppliers
- Introduce/Enhance cross-selling of Accessories:  Identify specific types of accessories to be offered for purchase with other categories.
#### Customer Segments
- Update analysis based on unique Customer ID (if available) 
- Assess/ Introduce a loyalty program 
#### Regional Comparisons
- Additional analysis (if data on Store ID and Store Location is available): Analyse average revenue per shop, shops profitability, regional distribution of shops 
- Investigate low performance of South region: contact sales representatives, conduct market research of the competitors
- Increase sales in regions with lower revenue: Introduce marketing activities targeting:
South as the lowest performing region
East as the region with the lowest profit margin (specifically, Accessories)
### Clarifying Questions, Assumptions, and Caveats
#### Questions for Stakeholders Prior to Project Advancement
- Is the data on unique Customer ID attributed to each customer stored? 
- Is data on Shop ID, Shop Location stored?
- Is there a loyalty program at Bowman Goods?

#### Assumptions and Caveats
We assumed that a unique combination of name and surname of a customer represents a unique client, since the dataset did not include a unique customer ID. Customer analysis should be interpreted with caution.

### Annex 1. Sales Dashboard
<img width="1326" height="744" alt="image" src="https://github.com/user-attachments/assets/0bb2b701-e861-4208-9799-317e91c51386" />

