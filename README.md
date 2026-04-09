# Power BI Project: Business performance, market expansion & choosing strategic products analysis


## I. Business requirements
### Business questions: 
- How is the overall business performing currently?
- Which markets show the highest potential for expansion?
- Which categories, sub-categories, or products should be prioritized for investment?

=> The company is currently prioritizing **GROWTH** as its main strategy.

### Company context: 
Superstore is a global retail company experiencing strong growth across multiple markets. The **Senior Sales Manager** wants an overview to identify which markets have the highest potential for expansion, as well as which products should be prioritized for strategic planning.

## II. Design thinking process
This project applies the 5-step Design Thinking framework to deeply understand Sales Manager's needs behind the business questions, and to deliver a highly relevant dashboard that effectively supports decision-making.

### 1. Empathise 
This step focuses on analyzing business requirements, clarifying stakeholder needs using the 5W1H framework, and developing a clear understanding of the dataset.

a. Analysing business problem


<img width="900" height="310" alt="image" src="https://github.com/user-attachments/assets/a93bf2db-8be9-44bb-959f-b85de72604a0" />

b. Analysing stakeholders


<img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/3ac0c663-e109-4b88-a048-864ffbedc642" />


c. Understanding dataset

<img width="270" height="310" alt="image" src="https://github.com/user-attachments/assets/f911bc2a-bf2e-4ca4-b356-5786777f64cd" />



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
Top three market that generated the highest revenue are  APAC (3.59M, accounted for 28.36%), EU (2.94M accounted for 23.24%) and US (2.3M  accounted for 18.17%). The ratio of three categories was relatively balanced across most markets, but the Technology still hold the largest share. 

The most common product in these markets were Bookcase, Phone, Chair. However, in EU market, Copier uniquely generated the highest revenue. 

In terms of CAGR, Canada witnessed the strongest growth (28.45%), followed by Africa (22.14%), though these were two markets with the lowest revenue. Despite one of the three largest markets, US experienced the lowest growth, approximately 10%. 

By country, US generated the highest amount of revenue (2.2M), equals 2.4 times that of the second highest country. 
### Product
All product categories were seasonal, with the total sales increased significantly toward the end of the year. 

Technology and Office Supplies had the highest percentage of Gross Profit Margin (13.99% and 13.69%, respectively), which is double that of the Furniture category with a margin of only 6.94%.

Four sub-categories that were the most significant revenue contributors were: Phones (1.7M), Copiers (1.5M), Chairs (1.5M), Bookcase(1.4M). 

Sub-categories that had the highest Profit Margin were: Paper (24.24%), Labels (20.45%), Envelopes (17.32%), Accessories (17.29%), Copier (17.13%). However, only Copier and Accessories had high revenue. The remaining products were among the five with the lowest revenue in the entire company.

In particular, Tables had a negative Profit Margin (-8.46%) despite having fairly high revenue (749K).

## 4. Recommendations
- Need deeper research on the reason why total sales had tendency to decrease sharply in the first quarter each year, to propose the appropriate business strategy.
- Continue to develop in major markets (APAC, EU), while expanding and researching on high-potential markets such as Canada and Africa. The US, despite one of the largest market, it was required a new business strategy to push the sales.
- Intensify marketing campaigns in third and forth quarters, most focus on potential product (with low sales but high profit margin) such as Accessories, Art, Papers, Evelopes besides Phones, Bookcases, Copier, Chair groups which were company's strength.
- Bên cạnh đó, đẩy mạnh các hoạt động upsale, cross-sale để tăng giá trị đơn hàng.
- In addition, enhance upsale and cross-sale to increase cart value
