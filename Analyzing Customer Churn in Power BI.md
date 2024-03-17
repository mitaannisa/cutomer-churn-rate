# Analyzing Customer Churn in Power BI


### The Problem
Discover why customer are churning from a fictious dataset about churn from a telecom provider (Databel)

#### Defining Churn
The churn rate, also known as the rate of attrition or customer churn, is the rate at which customers stop doing business with an entity

#### Calculating churn
Churn rate = customers lost / total number of customers

### The Data
Key characteristics:
- one big table containing 29 columns
- one row per customer
- snapshot of the database at a specific moment in time

Dimensions
| Column name | Description |
| ------ | ------ |
| Customer_id | The unique ID that identifies a customer |
| Churn label | Contains 'Yes' or 'No' to indicate if a customer churned |
| Demographic fields | Age, Gender, State, ... |
| Premium plans | Unlimited data, international Plan, ... |
| ... | ... |

Measures
| Column name | Description |
| ------ | ------ |
| Total charges | Sum of all monthly charges |
| Monthly charges | The average of all monthly charges billed to the customer |
| Extra data charges | Extra charges for data downloads above the specified customer |
| Extra international charges | Extra charges for internatiomal calls for customers not on an international plan |
| ... | ... |

##### Data check
To kickstart the analysis, a data check measure will be created to ensure that the count of unique customer IDs aligns with the total count of customers. This crucial step eliminates the possibility of duplicate rows and potential misinterpretation of costs.

![datacheck](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/5cda6b85-1e6a-40ce-aae6-fbfbbe993f23)
##### Churn Rate
The churn rate will be calculated next by creating a new measure called "Churn Rate" with the simplified formula: Churn Rate = Customers Lost / Total Number of Customers
resulting in a churn rate of 26.86%.

![churn_rate](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/2b9feacb-a9f2-420d-a429-43b1e637318a)
##### Churn Category
Next, it is important to know the churn category based on the churn reasons. A bar chart was created to display churn category in descending order. The chart showed that "Competitor" category has the highest number of customers, accounting for 805 customers.

![churn_category](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/08c0a6c9-255f-4a95-b4b6-bf149aafcd55)
##### Churn Rate by State
The map illustrates geographical variations in churn rate across different states. This helped identifying regions with the highest churn rates, uncovering potential factors contributing to customer attrition in specific geographic locations, and informing targeted marketing or service improvement efforts tailored to regional needs.

![map](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/c3712c41-0823-472b-91c9-55b32dacf17b)
The highest churn rate of 63.24% is experienced by California, with 43 customers churning. The reasons for this high churn rate warrant further investigation, which is something to be highlighted to Databel.

![map_2](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/cdb54fc0-187e-490a-8888-1a9543edf5ea)
##### Churn Rate by Age
Uncovering interesting insights about customer age is considered crucial for this analysis. In this dynamic line and stacked column chart, the number of customers in each age bracket and their corresponding churn rate are observed.

![age](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/63ad1262-92c0-4a67-8424-3042c50f6fe7)
- An analysis of customer age brackets indicates a consistent upward trend in churn rate as age increases. 
- The highest churn rate is 52% on a 85 years old customers.
##### Churn Rate by Groups
Group contracts are provided by Databel to customers residing in the same household, offering a discounted rate, which serves as a great incentive for expanding their customer base. To assess the impact of group contracts on monthly charge and churn rate, an interactive line and stacked column chart has been implemented.

![inspecting_groups](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/0fccb791-9eca-4e10-bb04-643063dc1074)
- The lowest churn rate is from the group plan with 6 number of customers in group at 5.60%
##### Churn Rate by Gender and Contract Type
Customer contract type classified as three options: "Month-to-Month", "One Year", and "Two Year". Then we categorized the contract type into a contract category "Monthly" and "Yearly" and displayed using multi row card. Moreover, churn rate by contract category and gender is displayed in a clustered bar chart.

![multiple_fields](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/5f9d4d03-3c16-4c4f-a048-f12827711c33)
- Monthly contract category has highest churn rate at 46.29%
- Among customers with monthly contracts, females encounter a highest churn rate of 47.31%, males face 45.31%, while those opting not to disclose their gender experience a churn rate of 40%.
- Among a yearly contract, females demonstrate a relatively low churn rate of 6.02%, whereas males have a slightly higher churn rate of 7.21%.

##### Churn Rate by Unlimited Plan 
Customer unlimited data plan likely to effect the churn rate. The table showcase the comparison between churn rate of customer with unlimited data plan and without unlimited data plan. 
Next, new column has been generated to categorize the average monthly GB downloads into three groups consumption: "10 or more GB", "Between 5 and 10 GB", "Less than 5 GB".

![unlimited_plan](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/87a1eb7a-3a03-46fa-a8aa-eec32227d959)
- The highest churn rate is found among customers with unlimited data plans who consume less than 5 GB, which is 34.71%. 
- Meanwhile, for the category without unlimited data plans, the highest churn rate is observed among customers with consumption between 5 and 10 GB, which is 31.78%.
##### Churn Rate by International Calls
In this term of analysis, matrix has been created to revealing churn rates based on two dimensions: International Plan (row) and International Activity (column). The International Plan indicates whether customers have a premium plan enabling them to make international calls for free, while International Activity indicates whether customers actively engage in international calls.
Next, Maps are utilized to display churn rate and customer service calls based on state.

![international_calls](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/bfaa8326-72be-42c3-b9c0-128abd3de90c)
- Churn rate of 71.19% is observed among customers who have an international plan but do not actively make international calls. It is essential for Databel to proactively engage with these customers and offer plan downgrades.
- California has a high churn rate of 63.24%. Databel can strategically allocate their budget for promoting the new international plan, targeting this region to achieve maximum impact.
##### Churn Rate by Account Lengths
The churn rate decreases proportionally with the length of customer subscription to Databel. Therefore, Databel needs to enhance its services to maintain long-term relationships with customers.

![contract_type1](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/fe790c90-ef1e-4860-8677-214e5c4ecc37)
The churn rate is also influenced by the contract type, as previously shown, and then combined with the account length.

![contract_type2](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/565a72ef-3f45-49c9-a088-6409d09adfee)
The pie chart here illustrates the influence of payment methods on churn rate. As seen in the pie chart, the paper check payment method has a high churn rate of 43.70%.

![contract_type3](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/1915e2ed-5074-4f2c-a3a9-227877cb58ef)
##### Dashboard Overview
This dashboard overview consists of three important pieces of information: the number of customers, the number of churned customers, and the churn rate. Additionally, it also includes:
- Bar chart illustrating churn reasons and their corresponding customer counts
- Donut chart displaying the contract types of customers
- Pie chart depicting churn customers based on churn categories
- Maps showing the distribution of churn rate by state

![overview](https://github.com/mitaannisa/cutomer-churn-rate/assets/90240765/5f24f919-5587-4fe3-bf31-546816fcb166)

















