# Project 2: Power_BI_Superstore_Sales
# I. Introduction
## 1. Business requirements
Superstore is an global retail company. The head of Sales department wanted to know about current sales situation. Hence, he will ideate the appropriate strategies to choose strategic products and expand the market share. 


## 2. Business analysis using Design thinking 
### 2.1 Empathise
<img width="629" alt="image" src="https://github.com/mistletoegoegoe/Power_BI_Superstore_Sales/assets/121160527/2a1604c6-fd0e-41aa-9ae2-5fa3da12bfe2">

### 2.2 Define
<img width="629" alt="image" src="https://github.com/mistletoegoegoe/Power_BI_Superstore_Sales/assets/121160527/8a408a6f-2f37-496c-82fd-5d3af06ba738">

### 2.3 Ideate
<img width="677" alt="image" src="https://github.com/mistletoegoegoe/Power_BI_Superstore_Sales/assets/121160527/65a8c55b-8846-466b-bc14-f179f4584ac7">

### 2.4 Prototype and review
<img width="680" alt="image" src="https://github.com/mistletoegoegoe/Power_BI_Superstore_Sales/assets/121160527/466f9474-aa0d-4702-9b74-14e48d48af59">

## 3. Data dictionary
There are 3 data tables: 
- Orders: it was the fact table that contained all relevant information about each order_ID. It comprised time-related attributes, customer's information, market area, product details
- People: it contained name of salemen and the region that they were in charge of. 
- Returns: this table recorded the data about returned orders
### Table Orders
| Field          | Meaning                               |
|----------------|---------------------------------------|
| Order ID       | Unique ID of each order               |
| Order Date     | The date that order had been made     |
| Ship Date      | The date that order had been shipped  |
| Ship Mode      | The type of shipment                  |
| Customer ID    | Unique ID of customer                 |
| Customer Name  | Name of customer                      |
| Segment        | Customer segmentation                 |
| City           | City where order had been made        |
| State          | State where order had been made       |
| Country        | Country where order had been made     |
| Postal Code    | Postal code where order had been made |
| Market         | Market area of the order              |
| Region         | Region of order                       |
| Product ID     | Product unique ID in the order        |
| Category       | Category of product                   |
| Sub-Category   | Sub-category of product               |
| Product Name   | Product name                          |
| Sales          | Total revenue of order                |
| Quantity       | Total quantity of products in order   |
| Discount       | % discount for the order              |
| Profit         | Profit of the order                   |
| Shipping Cost  | Shipping cost for the order           |
| Order Priority | The level of priority                 |

### Table People
| Field  | Meaning                            |
|--------|------------------------------------|
| Person | The saleman who was in charge of   |
| Region | The region he/she was in charge of |

### Table Returns
| Field    | Meaning                               |
|----------|---------------------------------------|
| Returned | Yes/no - the status of returned order |
| Order ID | Unique ID of the order                |
| Market   | The market that had returned order    |
# II. Data visualisation
## 1. DAX
By the given data, there is no available Sales per order metric, which was necessary to provide an overview about Sales situation. Thus, a measure was created to calculate this indicator. The calculation would be implemented in DAX.
### Sales per order formula:
Cart value = Total sales / Total orders
### DAX code
```
Cart value = round((divide(sum(Orders[Sales]),DISTINCTCOUNT(Orders[Order ID]))),2)
```
## 2. Dashboard
<img width="671" alt="image" src="https://github.com/mistletoegoegoe/Power_BI_Superstore_Sales/assets/121160527/ab3f18bc-82e4-4e7f-bd6c-e5fee5262825">

## 3. Insights
### Overall 
Sales remained the increasing tendency from 2011 to 2014 with a compound annual growth rate (CAGR) of 17.46%. However, within each year, there was a common pattern that total sales showed an upward trend across all product categories until forth quarter, before falling down in the first quarter of the next year. 

Gross Profit Margin remained stable around 11% throughout 4 years. 

Cart value did not vary much across the years, while the number of order increased significantly over years (1.7 times in 2014), which contributed to the overall sales of the company. 

The value of returned order showed a slight upward trend over years with the average value being 1.3 times of successful orders. The significant markets were APAC (32%), US (22%), EU (25%), and LATAM (20%).

B2C segment is the most significant contributer to company's revenue (51%), followed by Corporate (30%) and Home Office. However, in recent years, the sales of these groups had a slight downward trend. Home Office tended to increase in the structure of total revenue in 2014. 

### Market
### Product
## 4. Recommendations
