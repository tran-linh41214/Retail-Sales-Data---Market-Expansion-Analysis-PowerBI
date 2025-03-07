# Superstore-Sales



---
![E-commerce Website_Analysis](https://github.com/Dorothy-Ho-Vy/Sample-Readme-template/blob/0e47d32968459ec80d7d2666fbf5044ac56894e6/1.png)

Change Icon emoji 🔥🔍📘🚩 to your likings by clicking "Start" + "."

# 📊 Project Title:  [Global_Superstore_Sales]  
Author: [Tran Linh]    
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
 
This project analyzes global sales performance using Power BI. The objective is to:

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
Summarize key findings and insights/ trends/ themes in a concise, bullet-point 
format.  

 _Example:_

✔️ Sales Trends: The top X% of products generate Y% of revenue.  
✔️ Inventory Optimization: Certain products are frequently out-of-stock, causing revenue loss.  
✔️ Customer Behavior: Returning customers spend Z% more per transaction than new customers.  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  
- Source: The dataset contains global sales information of a company called Superstore.   
- Format: .csv  

### 📊 Data Structure & Relationships  

#### 1️⃣ Tables Used:  
**Three tables:**

- **Orders:** Stores transaction information.
- **People:** Contains details of sales representatives in each region.
- **Returns:** Records transactions that were returned.  

#### 2️⃣ Table Schema & Data Snapshot  

Table 1: Orders  


### **Orders Table**
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



Table 2: People  

### **People Table**
| Column Name | Data Type | Description |
|------------|----------|-------------|
| Person     | TEXT     | Name of the person |
| Region     | TEXT     | Region associated with the person |  


Table 3: Returns  

| Column Name | Data Type | Description |
|------------|----------|-------------|
| Returned   | TEXT     | Indicates if the order was returned (Yes/No) |
| Order ID   | TEXT     | Unique identifier for each order |


#### 3️⃣ Data Relationships:  
  

![image](https://github.com/user-attachments/assets/ac04984d-f32e-475f-9c53-3f38fe9764a7)
 

---

## 🧠 Design Thinking Process  

Explain the step-by-step approach taken to solve the problem.  

👉🏻 Insert a screenshot of the Design Thinking steps (Screenshot your Excel design thinking tables for better presentation).  

1️⃣ Empathize  

![image](https://github.com/user-attachments/assets/281fd807-6902-41b2-b285-7072bb3e6a97)

![image](https://github.com/user-attachments/assets/9e25f73d-2c4f-4793-8a93-aebdcd37088c)

![image](https://github.com/user-attachments/assets/839e31e2-2d6b-4611-b241-25984573a845)

![image](https://github.com/user-attachments/assets/56abd9a1-33b1-4f5f-b294-d94c6b04a86e)


2️⃣ Define point of view  

![image](https://github.com/user-attachments/assets/a32cccdb-b020-4cc6-a0be-9da62f8bdaa9)

![image](https://github.com/user-attachments/assets/584dda10-497b-41ea-8453-72d9b094695c)


3️⃣ Ideate  

![image](https://github.com/user-attachments/assets/d515dc76-4cd0-435a-814c-c2438c04ba0d)

![image](https://github.com/user-attachments/assets/44e8a952-713e-4bd2-ab82-ba147f3cc1bd)


4️⃣ Prototype and review  

---

## ⚒️ Main Process

1️⃣ Data Cleaning & Preprocessing  
2️⃣ Exploratory Data Analysis (EDA)  
3️⃣ SQL/ Python Analysis 

- In each step, show your Code

- Include query/ code execution screenshots or result samples

- Explain its purpose and its findings

  **Metric**

```power BI
Total_orders = DISTINCTCOUNT(Orders[Order ID])

Total_profit = SUM(Orders[Profit])

Total_sale = SUM(Orders[Sales])
```

```power BI
avg_delivery_time = AVERAGE(Orders[Delivery_time])
```

```power BI
avg_total_sale_all = 
 VAR total_sale =
 CALCULATE(SUM(Orders[Sales]))
 VAR total_orders =
 CALCULATE(DISTINCTCOUNT(Orders[Order ID]))
 RETURN
total_sale / total_orders
```

**PY - Previous Year**

```power BI
Total_orders_PY = CALCULATE([Total_orders], SAMEPERIODLASTYEAR(Dim_date[Date]))

Total_profit_PY = CALCULATE([Total_profit], SAMEPERIODLASTYEAR(Dim_date[Date]))

Total_sale_PY = CALCULATE([Total_sale], SAMEPERIODLASTYEAR(Dim_date[Date]))

```

**Measure**
**%change - % change vs previous year**

```power BI
%change_orders = DIVIDE([Total_orders] - [Total_orders_PY],[Total_orders_PY])

%change_profit = DIVIDE([Total_profit] - [Total_profit_PY],[Total_profit_PY])

%change_sale = DIVIDE([Total_sale] - [Total_sale_PY],[Total_sale_PY])

```

```power BI
%PF = DIVIDE([Total_profit],[Total_sale])
```

**Return metric**

```power BI
prduct_returned_count = calculate(count(Orders[Return label]),filter(Orders,Orders[Return label] = "Yes"))

Returned_Orders_count = CALCULATE(DISTINCTCOUNT(Orders[Order ID]), Orders[Return label] = "Yes")

Returned_orders_sale = CALCULATE(SUM(Orders[Sales]), FILTER(Orders, Orders[Return label] = "Yes"))

%return_orders = [Returned_Orders_count]/[Total_orders]

avg_returned_orders_deliverytime = CALCULATE(AVERAGE(Orders[Delivery_time]),filter(Orders,Orders[Return label] = "Yes"))

avg_returned_product_value = calculate(SUM(Orders[Sales]),Orders[Return label] = "Yes") / [prduct_returned_count]

```

4️⃣ Power BI Visualization  (applicable for PBI Projects)

---

## 📊 Key Insights & Visualizations  

### 🔍 Dashboard Preview  

#### 1️⃣ Dashboard 1: Overview

![image](https://github.com/user-attachments/assets/c8e12629-752b-4262-a177-07f7d1c3e91e)
 

📌 Analysis 1:  
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._  

- Sale và profit đều tăng khá nhiều so với năm trước (khoảng 25%)
- Mặt hàng table có profit âm (lỗ) -> cắt giảm mặt hàng này
- Khu vực South America có profit cao nhất

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
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._

Office Supplies profit cao nhưng AOV thấp => cần tăng bán kèm để nâng giá trị đơn => khuyến mãi product bán được ít trong category office supplies, các chương trình giảm giá khi mua kèm.
(Appliance đang có profit và AOV khá cao => có thể bán kèm các sản phẩm giá thấp hoặc bị trả lại nhiều (binder, art, paper), hoặc tặng kèm khi mua appliance.)

Furniture profit thấp, AOV cao => tăng profit => tìm cách giảm chi phí (thu hẹp thị trường), tăng giá bán 
Table: sale thấp trong khi tỷ lệ bị trả hàng cao => tìm nhà cung cấp khác hoặc bỏ mặt hàng này

Technology vừa có profit vao và AOV cao => tập trung vào category này
Trong Technology: Copier vừa có AOV cao vừa có profit cao, trong đó Hewllet copy machine là dòng máy bán chạy nhất

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

Would you like a deeper analysis on any specific metric? 🚀

#### 3️⃣ Dashboard 3: Sales by location  
👉🏻 Insert Power BI dashboard screenshots here  

📌 Analysis 3:  
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._

- United States là thị trường bán được nhiều đơn hàng nhất, đặc biệt là ở New York city 
Tại NYC thì các mặt hàng Technology, đặc biệt là phone bán chạy nhất. NYC cũng có tỷ lệ trả hàng thấp hơn trung bình => thị trường cần đẩy mạnh
Seattle có profit cao thứ 2 sau NYC, lĩnh vực có profit cao nhất cũng là technology, nhưng phần lớn đến từ copier, phone chỉ chiếm số ít
Sydney - Australia cũng có doanh số cao. Mặt hàng có profit cao nhất ở đây là Bookcase.
San Francisco là thành phố duy nhất trong top 5 profit có Office supplies chiếm tỷ lệ trong profit cao nhất, trong đó nhiều nhất là Art, sau đó là Label và envelopes



---

## 🔎 Final Conclusion & Recommendations  

Insight and Recommendation

OVERVIEW


PRODUCT

Office Supplies profit cao nhưng AOV thấp => cần tăng bán kèm để nâng giá trị đơn => khuyến mãi product bán được ít trong category office supplies, các chương trình giảm giá khi mua kèm.
(Appliance đang có profit và AOV khá cao => có thể bán kèm các sản phẩm giá thấp hoặc bị trả lại nhiều (binder, art, paper), hoặc tặng kèm khi mua appliance.)

Furniture profit thấp, AOV cao => tăng profit => tìm cách giảm chi phí (thu hẹp thị trường), tăng giá bán 
Table: sale thấp trong khi tỷ lệ bị trả hàng cao => tìm nhà cung cấp khác hoặc bỏ mặt hàng này

Technology vừa có profit vao và AOV cao => tập trung vào category này
Trong Technology: Copier vừa có AOV cao vừa có profit cao, trong đó Hewllet copy machine là dòng máy bán chạy nhất

MARKET

United States là thị trường bán được nhiều đơn hàng nhất, đặc biệt là ở New York city 
Tại NYC thì các mặt hàng Technology, đặc biệt là phone bán chạy nhất. NYC cũng có tỷ lệ trả hàng thấp hơn trung bình => thị trường cần đẩy mạnh
Seattle có profit cao thứ 2 sau NYC, lĩnh vực có profit cao nhất cũng là technology, nhưng phần lớn đến từ copier, phone chỉ chiếm số ít
Sydney - Australia cũng có doanh số cao. Mặt hàng có profit cao nhất ở đây là Bookcase.
San Francisco là thành phố duy nhất trong top 5 profit có Office supplies chiếm tỷ lệ trong profit cao nhất, trong đó nhiều nhất là Art, sau đó là Label và envelopes




👉🏻 Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:  

📌 Key Takeaways:  
✔️ Recommendation 1  
✔️ Recommendation 2  
✔️ Recommendation 3
