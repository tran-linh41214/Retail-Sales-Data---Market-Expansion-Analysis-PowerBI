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

1️⃣ Apply CodeM to create Dim_Date table 

| Column Name     | Description                            |
|-----------------|----------------------------------------|
| Date            | The specific date.                     |
| Year            | The year of the given date.            |
| Month           | The month of the given date.           |
| WeekofYear      | The week number within the year.       |
| WeekDay         | The day of the week for the given date.|

2️⃣ Apply DAX to calculate the metrics 

| _Calculation      | Description                              |
|-------------------|------------------------------------------|
| %margin_profit    | Percentage of margin profit              |
| %MoM_profit_rate  | Month-over-Month profit rate             |
| %MoM_revenue      | Month-over-Month revenue                 |
| %return_rates     | Percentage of return rates               |
| orders_count      | Number of orders                         |
| price_per_1item   | Price per one item                       |
| profit_per_1item  | Profit per one item                      |
| returns_count     | Number of returns                        |
| total_profit      | Total profit                             |
| total_quantity    | Total quantity of items                  |
| total_revenue     | Total revenue                            |


3️⃣ Power BI Visualization

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1: Overview

![image](https://github.com/user-attachments/assets/c8e12629-752b-4262-a177-07f7d1c3e91e)
 

📌 Analysis 1:  

  **Observations**  
1. **Overall Performance Growth:**  
   - Total sales reached **$4.30M**, a **26.25% increase** compared to the previous year ($3.41M).  
   - Total profit is **$504.17K**, showing a **23.89% improvement** over the previous year ($406.94K).  
   - Total orders increased to **8.53K**, a **26.93% rise** from last year (6.72K).  

2. **Sales Trend Over Time:**  
   - Sales showed a steady upward trend throughout 2014.  
   - Sales consistently outperformed the previous year, with visible seasonality and spikes in certain months.  

3. **Profitability by Product:**  
   - **Technology products** (especially **machines**) had the highest profit.  
   - **Tables** had negative profitability, indicating losses.  
   - Other categories had a mix of positive and negative margins, with some office supplies performing poorly.  

4. **Profitability by Region:**  
   - North America and Europe are performing well with positive profitability.  
   - Some regions (e.g., parts of Africa and Australia) show lower or neutral profitability.  

---

 **Recommendations**  
1. **Boost High-Performing Categories:**  
   - Invest in marketing and promotions for **Technology products**, especially machines, as they drive high profits.  
   - Expand inventory and logistics support for fast-selling, high-margin items.  

2. **Address Loss-Making Products:**  
   - Investigate why **Tables** are unprofitable—high costs, low demand, or pricing issues? Consider revising pricing, reducing costs, or discontinuing low-performing items.  
   - Analyze underperforming office supplies and make data-driven adjustments.  

3. **Leverage Regional Performance:**  
   - Expand efforts in **high-performing regions** (North America, Europe) with targeted campaigns.  
   - Explore pricing adjustments or localized strategies in **low-performing regions** to improve profitability.  

4. **Seasonal Sales Strategy:**  
   - Identify peak sales months and plan promotions, discounts, or inventory management accordingly.  
   - Prepare for expected demand spikes to avoid stockouts and maximize revenue.  


#### 2️⃣ Dashboard 2: Sales by product 

![image](https://github.com/user-attachments/assets/cdceff6b-34ec-4cde-a6ae-e31c0a98a214)


📌 Analysis 2:   

 **Observations**  

1. **Overall Order & Return Performance:**  
   - Total **25.04K orders** were placed.  
   - The **return rate is 4.68%**, indicating a moderate level of product returns.  

2. **Sales & Returns by Sub-Category:**  
   - Some sub-categories like **Binders, Storage, and Paper** have **high return rates** (Binders: 1,422 returns, Storage: 957 returns).  
   - **Tables and Chairs** also show significant returns in terms of value.  
   - High sales sub-categories like **Copiers, Phones, and Appliances** appear in the "Returned Product" section, suggesting issues in these categories.  

3. **Returned Product Impact:**  
   - The total value of returned orders is **$819.02K**.  
   - The **average product value** for returns is **$268.53**, indicating that costly items are being returned.  
   - The **average delivery time** for returned products is **3.91 days**, slightly lower than the **3.97-day average for all products**, suggesting potential quality or fit issues rather than late deliveries.  

4. **Top-Selling Products:**  
   - **Hoover Stove and Hoover Toaster** are among the best-selling products.  
   - Kitchen appliances dominate the top-seller list.  

5. **AOV (Average Order Value) and Profit:**  
   - Total sales are **$12.64M**, with an **AOV of $504.99**.  
   - Profit varies across sub-categories, with some high-AOV categories also showing moderate profits.  

---

 **Recommendations**  

1. **Reduce Return Rates for Key Sub-Categories:**  
   - Investigate **why Binders, Storage, and Paper** have high returns (quality, misleading descriptions, shipping issues?).  
   - Improve product descriptions, quality checks, or packaging for these categories.  

2. **Address High-Value Returns:**  
   - Since **Tables, Chairs, and Appliances** contribute to high return values, analyze reasons (defects, customer dissatisfaction, incorrect specifications).  
   - Consider stricter return policies or better customer education on product specifications.  

3. **Leverage Best-Selling Products:**  
   - The **Hoover brand (Stove, Toaster)** performs well—consider increasing stock or launching promotional campaigns to boost sales.  
   - Look into bundling kitchen appliances to increase overall basket size.  

4. **Optimize Delivery & Customer Support:**  
   - Since return delivery times are short, ensure customer feedback is analyzed for patterns (wrong item sent, damages, missing parts).  
   - Improve post-purchase support for expensive products to reduce returns.  


#### 3️⃣ Dashboard 3: Sales by location  

![image](https://github.com/user-attachments/assets/16e29668-3235-49c0-ab9b-7e6432760433)
 

📌 Analysis 3:    
 **Observations:**
1. **United States Dominance**:
   - The US leads in total orders, significantly outperforming other countries (1,704 orders).
   - New York City is a major contributor, excelling in Technology sales, particularly **phones**.
   - NYC also has a **lower return rate (3.47%)**, indicating customer satisfaction.

2. **Seattle's High Profitability**:
   - **Seattle ranks second** in profit.
   - While Technology is the top category, **copiers** generate most of the profit, with **phones contributing less**.

3. **Sydney’s Strong Sales**:
   - Australia ranks second in orders (513).
   - The highest profit-generating product in **Sydney is Bookcases**.

4. **San Francisco’s Unique Profit Mix**:
   - Unlike other top cities, **Office Supplies** dominate its profit.
   - Within this category, **Art, Labels, and Envelopes** are the key contributors.

**Recommendations:**
1. **Expand Technology Sales in NYC**:
   - Given the high demand and low return rate, **further investment in phone sales and marketing in NYC** can yield high returns.

2. **Enhance Copier Sales in Seattle**:
   - Copier sales should be **prioritized** in Seattle to maximize profit growth.
   - Consider **promotions or bundling offers** to encourage repeat purchases.

3. **Leverage Sydney’s Demand for Bookcases**:
   - Develop targeted **advertising campaigns and discounts** for Bookcases in Sydney.

4. **Capitalize on San Francisco’s Office Supplies Demand**:
   - Since **Art, Labels, and Envelopes** drive profits in SF, **optimize stock levels and marketing** for these products.



---

## 🔎 Final Conclusion & Recommendations  

#### **Conclusion:**  
The analysis of sales, products, and locations highlights strong performance in key markets, particularly the **United States**, with **New York City leading in sales and profitability**. **Seattle, Sydney, and San Francisco** also show strong potential, each excelling in specific product categories. **Technology, Office Supplies, and Furniture** drive overall revenue, while **return rates remain manageable**.  


#### **📌 Key Takeaways:**  
✔️ **Expand in High-Performing Markets** – Strengthen presence in **NYC and Seattle**, where sales and profitability are strong, with a focus on **Technology (Phones & Copiers)**.  
✔️ **Optimize Product Strategies** – Promote **Bookcases in Sydney** and **Office Supplies (Art, Labels, Envelopes) in San Francisco** to capitalize on regional demand.  
✔️ **Enhance Customer Retention** – NYC’s low return rate suggests a loyal customer base; replicating similar strategies in other regions can **reduce returns and boost repeat purchases**.  
✔️ **Drive Growth with Targeted Marketing** – Use **data-driven promotions, localized advertising, and product bundling** to improve engagement and maximize revenue. 
