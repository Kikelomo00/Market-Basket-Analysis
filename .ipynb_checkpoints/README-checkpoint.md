# Market Basket Analysis for E-commerce

## I. Introduction
## 1. Market Basket Analysis
Market basket analysis is a data mining technique that identifies customer purchasing habits and patterns to uncover associations between products frequently bought together. It involves analyzing transactional data from a retail or e-commerce environment to uncover associations between items bought in a single shopping session. It helps businesses understand consumer behaviour, optimize pricing strategies, and improve inventory management for increased profitability.

### Major types of Market Basket Analysis

Association Rule Mining: Identifies frequent item sets and generates association rules that express the likelihood of one item being purchased with the purchase of another item.

Sequence Analysis: Identifies frequent item sequences and generates sequential association rules describing the likelihood of one item sequence being followed by another.

Cluster Analysis: Groups similar items or transactions into clusters or segments based on their attributes to identify customer segments with similar purchasing behaviours.

### Objective of Market Basket Analysis
By identifying associations between products, retailers can strategically place related items near each other or offer personalized recommendations to increase sales and customer satisfaction. It helps improve inventory management, optimize product placement, and design effective marketing campaigns

## 2. Business questions
To uncover patterns in customer purchasing behaviour, we ask, "Which products  tend  to  be  bought  together in a single transaction?", to identify frequently purchased product combinations, then suggest promotions and cross-selling strategies.

## 3. About the Dataset
This dataset is a retail e-commerce that sells groceries. This dataset includes 38765 entries and 3 columns. The dataset is for transactions from 2014-01-01  to 2015-12-30

##### Overview of the dataset:
![Alt text](<Screenshot (259).png>)


## 4. About this Project
As this project aims to identify the associations between itemsets, the Association Rule Mining approach is adopted.

There are several algorithms used in Market Basket Analysis. This project will use the Apriori Algorithm, one of the most widely used and well-known algorithms used in Market Basket Analysis. It helps to find frequent itemsets in transactions and identifies association rules between these items.

### Apriori Algorithm

Some important metrics in Apriori Algorithm:


### i. Support
Support is a measure of how frequently an item or itemset appears in the dataset.  

![Alt text](Support.png)

High support indicates that an item or itemset is common in the dataset, while low support indicates that it is rare.

### ii. Confidence
Confidence is a measure of the strength of the association between two items.  

![Alt text](Confidence.png)

High confidence indicates that the presence of the first item is a strong predictor of the presence of the second item.

### iii. Lift
Lift is a measure of the strength of the association between two items, taking into account the frequency of both items in the dataset.  Lift is used to compare the strength of the association between two items to the expected strength of the association if the items were independent. 

![Alt text](lift.png)

A lift value greater than 1 indicates that the association between two items is stronger than expected based on the frequency of the individual items.  A lift value less than 1 indicates that the association is weaker than expected and may be less reliable or less significant.




In this project, the minimum support threshold that an itemset must meet to be considered frequent is identified at 0.06% in total number of transactions (0.06% of 14963, which is approx. 9).

Just because an item or itemset is common does not mean that there is a strong association between them. For example, the item "whole milk" may have a high support value, but that does not mean there is a strong association between coffee and any other particular item.

Therefore, we should also consider the lift metric when assessing the associations between items, as it takes into account the support of each item to measure the strength of the association between them.

lift{A,B} = 1: no relationship between A and B (A and B occur together only by chance).
lift{A,B} > 1: positive relationship between A and B ( A and B occur together more often than random).
This project will set the minimum threshold for lift metric to 1.1 



Project Layout

The project will follow these steps:

1. Install the environment
2. Import and clean the dataset
3. Conduct simple EDA and Visualizations
4. Apply Apriori Algorithm to implement Market Basket Analysis


## II. Data Exploration and Visualizations
### 1. Quantity Sold by Days of Week
![Alt text](<vis 1.png>)

### 2. Top 30 Purchasing Customers
![Alt text](<vis 2.png>)

### 3. Top 30 Returning Customers
![Alt text](<vis 3.png>)

### 4. Top 20 Best Selling Items
![Alt text](<vis 4.png>)

### 5. Relationship between strong association and product purchasing frequency
![Alt text](<vis 5.png>)

### 6. Itemsets Lift
![Alt text](<vis 6.png>)

## Insights
1. Although Thursday is the day with the highest sold items,the difference between the quantity of items sold in other days can be considered negligible,thus we cannot say Thursday is the busiest day
2. Top purchasing customers (customers that have bought the most goods) are not top returning customers. Why? How do we retain top purchasing customers?
3. Whole milk is the highest purchased item accounting for approximately 16% of items bought
4. 3 fruits(tropical fruit, citrus fruit and pip fruit) are one of the best-selling items but looking at the least sold items, we can see a particular fruit, frozen fruit which has barely made sales, what could be the reason for this?
5. Something similar is also seen with root vegetables and other vegetables are one of the best selling items but specialty vegetable is one of the least-sold items 

## Market Basket Analysis
1. There are 520 association rules found with min_support = 0.0006 and min_lift = 1.1
2. The itemset, sausage and yoghurt, have the highest support value indicating they are common in the dataset. They have high support values individually and together
3. The scatterplot reveals that less common itemsets (those with lower support/occurrence rates) tend to have higher lift values. This means when those less frequent item pairs or groups appear together in purchases, they are more likely to be bought together intentionally rather than by chance. So less common itemsets can still have strong associations, even though they occur less frequently overall. 
4. Hamburger meat and soft cheese have the highest lift value (2.7) indicating they are most frequently bought together, despite being a small percentage (2% and 1%) of total itemsets.
5. Whole milk(the most purchased item) has strong associations with sausage pork (lift 2.4) and brandy (lift 2.2).

## Recommendations
1.  Strategically placing items with high lift values near each other on shelves could increase joint purchases e.g(hamburger meat and soft cheese, whole milk, sausage pork and brandy, and other strong associations)
2. Investigate why top purchasing customers are not returning customers
3. Investigate what makes frozen fruit different from the other types of fruit sold and maybe it should not be sold anymore
4. Investigate what makes specialty vegetables different from the other types of vegetables sold and maybe they should not be sold anymore
