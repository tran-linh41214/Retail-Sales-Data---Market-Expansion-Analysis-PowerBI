# Retail Sales Data - Market Expansion Analysis | PowerBI



---

# 📊 Project Title:  Retail Sales Data - Market Expansion Analysis | PowerBI 
Author: Tran Linh    
Tools Used: Power BI  

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### Objective:
### 📖 What is this project about? 
 
This project analyzes global stationery sales performance using Power BI. The objective is to:

- Identify top-performing products and regions for market expansion
- Minimize losses by analyzing return trends
- Support data-driven decision-making for product strategy  

### 👤 Who is this project for?  


✔️ Sales Manager  
✔️ Marketing Manager  
✔️ Customer Service Department  / Customer Experience Department

###  ❓Business Questions:  

✔️ What are the top-performing products and regions for sales growth?  
✔️ Which products have the highest return rates, and why?  
✔️ How can sales trends help optimize market expansion strategies?  
✔️ What factors contribute to revenue fluctuations across different segments?

### 🎯Project Outcome:  
✔️ **Sales Performance:** The United States dominates in sales, with New York City leading in both revenue and profitability. Other high-performing cities include Seattle, Sydney, and San Francisco.

✔️ **Product Insights:** Technology (Phones & Copiers) drives profit in NYC and Seattle, while Bookcases perform well in Sydney. San Francisco stands out for Office Supplies, especially Art, Labels, and Envelopes.

✔️ **Return Rate Analysis:** NYC has a lower-than-average return rate, making it a high-potential market for growth. Other regions should adopt best practices to reduce returns and increase customer satisfaction.

✔️ **Regional Growth Potential:** Seattle has strong profit potential in Copiers, while Sydney excels in Furniture. Targeted expansion strategies can further boost revenue. 

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: The dataset contains global sales information of a stationery company called Superstore.  
[🧷link to the dataset](https://drive.google.com/drive/folders/1oGbuHPBQECXKUcbhjuYOgk-ZH55Uau-g?usp=drive_link)  
- Format: .csv  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
**Three tables:**

- **Orders:** Stores transaction information.
- **People:** Contains details of sales representatives in each region.
- **Returns:** Records transactions that were returned.  

#### 2️⃣ Table Schema & Data Snapshot  

<details>
  <summary>📌 Click for detail</summary>

  <details>
  <summary>Table 1: Orders</summary>

| Column Name   | Data Type | Description |
|--------------|----------|-------------|
| Order ID     | TEXT     | Unique identifier for each order |
| Order Date   | DATE     | Date when the order was placed |
| Ship Date    | DATE     | Date when the order was shipped |
| Ship Mode    | TEXT     | Shipping method used for the order |
| Customer ID  | TEXT     | Unique identifier for the customer |
| Customer Name | TEXT    | Name of the customer |
| Segment      | TEXT     | Segment classification of the customer |
| City         | TEXT     | City where the order was placed |
| State        | TEXT     | State where the order was placed |
| Country      | TEXT     | Country where the order was placed |
| Postal Code  | TEXT     | Postal code of the shipping address |
| Market       | TEXT     | Market category for the order |
| Region       | TEXT     | Region classification for the order |
| Product ID   | TEXT     | Unique identifier for the product |
| Category     | TEXT     | Category of the product |
| Sub-Category | TEXT     | Sub-category of the product |
| Product Name | TEXT     | Name of the product |
| Sales        | FLOAT    | Sales revenue from the order |
| Quantity     | INT      | Number of items in the order |
| Profit       | FLOAT    | Profit earned from the order |

  </details>

  <details>
  <summary>Table 2: People</summary>  

| Column Name | Data Type | Description |
|------------|----------|-------------|
| Returned   | TEXT     | Indicates if the order was returned (Yes/No) |
| Order ID   | TEXT     | Unique identifier for each order |  

</details>

  <details>
  <summary>Table 3: Returns</summary>  

| Column Name | Data Type | Description |
|------------|----------|-------------|
| Person     | TEXT     | Name of the person |
| Region     | TEXT     | Region associated with the person |  

</details>

</details> 


#### 3️⃣ Data Relationships:  
  

![image](https://github.com/user-attachments/assets/ac04984d-f32e-475f-9c53-3f38fe9764a7)
 

---

## 🧠 Design Thinking Process  

Explain the step-by-step approach taken to solve the problem.  

👉🏻 Insert a screenshot of the Design Thinking steps (Screenshot your Excel design thinking tables for better presentation).  

1️⃣ Empathize  

<p align="center">
  <img src="https://github.com/user-attachments/assets/281fd807-6902-41b2-b285-7072bb3e6a97" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/9e25f73d-2c4f-4793-8a93-aebdcd37088c" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/839e31e2-2d6b-4611-b241-25984573a845" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/56abd9a1-33b1-4f5f-b294-d94c6b04a86e" alt="Description">
</p>


2️⃣ Define point of view  

<p align="center">
  <img src="https://github.com/user-attachments/assets/a32cccdb-b020-4cc6-a0be-9da62f8bdaa9" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/584dda10-497b-41ea-8453-72d9b094695c" alt="Description">
</p>


3️⃣ Ideate  

<p align="center">
  <img src="https://github.com/user-attachments/assets/d515dc76-4cd0-435a-814c-c2438c04ba0d" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/44e8a952-713e-4bd2-ab82-ba147f3cc1bd" alt="Description">
</p>


4️⃣ Prototype and review  

---

## ⚒️ Main Process

1️⃣ Create Dim_Date table 

| Column Name     | Description                            |
|-----------------|----------------------------------------|
| Date            | The specific date.                     |
| Year            | The year of the given date.            |
| Month           | The month of the given date.           |
| Quarter         | The quater of the given date.       |
| WeekDay         | The day of the week for the given date.|

2️⃣ Apply DAX to calculate the metrics 

| _Calculation      | Description                              |
|-------------------|------------------------------------------|
| %margin_profit    | Percentage of margin profit              |
| %change_orders    | Year-over-Year total orders              |
| %change_sale      | Year-over-Year total revenue             |
| %change_profit    | Year-over-Year total profit              |
| %return_orders     | Percentage of return rates               |
| total_orders      | Number of orders                         |
| total_sales       | Total revenue    |
| total_profit      | Total profit   |
| avg_total_sale_all   | Average order value                       |
| average_delivery_time  | Average delivery time per order                      |
| Returned_Orders_count | Number of returns                        |
| Returned_orders_sale | Total value of returned orders  |
| avg_returned_orders_deliverytime | Average delivery time per returned order |
| avg_returned_product_value | Average returnes order value  |


3️⃣ Power BI Visualization

⚡ Dashboard 1: Sales Overview  

![image](https://github.com/user-attachments/assets/9cb7450a-48fe-4736-a107-cb1f33619701)

⚡ Dashboard 2: Sales by Product

![image](https://github.com/user-attachments/assets/d649aa06-beef-4671-a3c0-0f2bd499156a)

⚡ Dashboard 3: Sales by Market

![image](https://github.com/user-attachments/assets/7f93aeba-ab6b-4b05-9eb0-dcd92fae27cf)


 
---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1: Sales Overview

![image](https://github.com/user-attachments/assets/573eafc7-e02d-411f-9b2d-01e4a4f1f064)


📌 Analysis:  
✅ Sales and profit have grown significantly compared to the previous year (around 25%).  
✅ The "Table" product has negative profit → Consider discontinuing or optimizing it.  
✅ South America has the highest profit, while Africa and Canada contribute the least.  
✅ The Technology category has the highest margin, while Furniture has lower profitability.  
✅ APAC and EU are the top-performing markets in terms of total sales.
  


#### 2️⃣ Dashboard 2: Sales by product 

![image](https://github.com/user-attachments/assets/9bc1002c-99f9-41d6-a953-ff5f4a515b5d)



📌 Analysis 1:   Key Summary Metrics  
✅ 25.04K Orders: Total number of transactions, reflecting sales volume.
✅ 4.68% Return Rate: A relatively high return rate, requiring investigation into the causes.

📌 Analysis 2:  Returned Product Analysis  

<p align="center">
  <img src="https://github.com/user-attachments/assets/4307d530-82cf-4008-9cb3-2310510443a5" alt="Description">
</p>


✅ **Total Return Value:** $819.02K, a significant amount that impacts profitability.  
✅ **AOV of Returns:** $268.53, indicating that the average value of a returned order is relatively high.  
✅ **Quantity of Returned Products:** Binders have the highest return count (1,422 units), followed by Storage, Paper, and Art.  
➡️ It’s important to investigate the reasons behind returns and consider improving quality control or adjusting return policies.

📌 Analysis 3: Product Performance

<p align="center">
  <img src="https://github.com/user-attachments/assets/dde1bd1f-4c27-4a35-be30-69d03ef0b384" alt="Description">
</p>


✅ **Total Revenue:** $12.64M, representing overall product sales.  
✅ **AOV (Average Order Value):** $504.99, indicating the average value per order.  
✅ **AVG Delivery Time:** 3.97 days, the average time taken to deliver orders.    
✅ Some categories have high AOV but do not yield high profits, suggesting a need to optimize pricing and cost structures.    

<p align="center">
  <img src="https://github.com/user-attachments/assets/1593e03e-c656-47ad-8a52-3f92ed614ca0" alt="Description">
</p>


✅ Phones, copiers, and chairs generate the highest revenue.  
✅ Some subcategories have high return rates despite lower sales, which may indicate quality issues or mismatches in customer expectations.  

**⏩ Recommendation**  

➡️ **Reduce Returns** – Improve quality or descriptions for **Binders, Storage, and Paper** to lower high return rates.  
➡️ **Boost Best-Sellers** – Ensure stock & promote **Hoover Toaster, KitchenAid Blender** for higher sales.  
➡️ **Re-Evaluate Low Performers** – Consider cutting or improving **Tables & Accessories** due to low profit/high returns.  
➡️ **Maximize High AOV Products** – Optimize pricing & sales strategy for **Copiers & Appliances** to increase profit.  
➡️ **Enhance Delivery** – Optimize logistics to improve the **3.97-day avg. delivery time**.  


#### 3️⃣ Dashboard 3: Sales by Market  

![image](https://github.com/user-attachments/assets/9515d35c-2f42-421c-a0c5-52ffa312c0ae)

 
📌 Analysis 1: Revenue & Orders Overview  



✅ Total Revenue: $12.64M, with 25.04K total orders.  
✅ Avg. Margin Profit: 11.61%, which is decent but can be optimized.  
✅ Avg. Return Rate: 4.68%, with 47.28% orders returned within 60 days.  

📌 Analysis 2: Market performance  

<p align="center">
  <img src="https://github.com/user-attachments/assets/dd6a26e3-9c78-47ff-8668-ee67e491f7d2" alt="Description">
</p>


✅ **APAC & LATAM** have higher orders but high return rates (5.8%-6.9%).  
✅ **Canada** has the highest margin profit (26.62%), suggesting strong pricing power.  

<p align="center">
  <img src="https://github.com/user-attachments/assets/670a7d5c-419a-4de0-bd5f-9683ab246702" alt="Description">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/2777739a-cb06-4e5c-aafd-0a1f0569a101" alt="Description">
</p>


✅ The Central region leads in overall market revenue and has a stable YoY revenue growth of 45.05%. Its return rate is also approximately at the average level (4.91% vs. 4.68%), indicating an effective sales strategy.

📌 Analysis 3: Segment Analysis  


<p align="center">
  <img src="https://github.com/user-attachments/assets/6467767c-5f5c-4602-9b3a-42b43d172c51" alt="Description">
</p>


✅ **Corporate** segment has the highest number of orders but also a high return rate of 4.93%.  
✅ **Home Office** segment has lower revenue and returns, showing stable performance.  

📌 Analysis 4: Employee & Product performance

<p align="center">
  <img src="https://github.com/user-attachments/assets/eab21d19-c847-44ff-9b30-043d8ffea226" alt="Description">
</p>


✅ Anna Andreadi handles a large share of orders, particularly Binders, Storage, and Paper, which have high return rates (4.6%-5.28%).  
✅ Technology (Copiers, Phones) generates high revenue, but accessories have low revenue impact.  



---

## 🔎 Final Conclusion & Recommendations  
  

| **Category**        | **Key Insights** | **Recommendations** |
|---------------------|----------------|---------------------|
| **Overall Market Performance** | - Total revenue: $12.64M, steady YoY growth.  <br> - Return rate: 4.68%, within acceptable limits. | - Continue current market strategy while optimizing high-performing segments. <br> - Reduce returns by improving product quality and customer service. |
| **Regional Analysis** | - **Central region** leads in revenue with stable 45.05% YoY growth. <br> - **South region** shows promising revenue but has slightly higher return rates. <br> - **Canada** and **Africa** have lower sales and profit margins. | - Expand product availability in Central region and maintain strong supply chain efficiency. <br> - Investigate reasons for returns in South and implement quality checks. <br> - Develop targeted marketing and promotional strategies for Canada & Africa to boost sales. |
| **Segment Performance** | - **Consumer segment** generates the highest orders. <br> - **Corporate segment** has the highest return rate (~4.93%). | - Enhance B2C strategies through discounts and personalized marketing. <br> - Improve after-sales service for corporate clients to reduce returns. |
| **Category & Product Insights** | - **Technology** and **Office Supplies** drive most revenue. <br> - **Furniture** has lower margin profit and higher return rates. <br> - **Binders, Chairs, and Storage** have the highest return quantity. | - Invest in marketing and expanding Technology & Office Supplies. <br> - Review and reconsider Furniture product lines, focusing on best sellers. <br> - Improve quality control on high-return products and introduce better return policies. |
| **Employee Performance** | - Certain employees handle high-value transactions (e.g., Anna Andreadi). | - Provide incentives and training to high-performing employees to sustain growth. <br> - Analyze underperforming employees and provide targeted support. |


