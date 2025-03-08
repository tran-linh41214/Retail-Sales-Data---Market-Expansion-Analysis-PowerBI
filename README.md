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
✔️ **Sales Performance:** The United States dominates in sales, with New York City leading in both revenue and profitability. Other high-performing cities include Seattle, Sydney, and San Francisco.

✔️ **Product Insights:** Technology (Phones & Copiers) drives profit in NYC and Seattle, while Bookcases perform well in Sydney. San Francisco stands out for Office Supplies, especially Art, Labels, and Envelopes.

✔️ **Return Rate Analysis:** NYC has a lower-than-average return rate, making it a high-potential market for growth. Other regions should adopt best practices to reduce returns and increase customer satisfaction.

✔️ **Regional Growth Potential:** Seattle has strong profit potential in Copiers, while Sydney excels in Furniture. Targeted expansion strategies can further boost revenue. 

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

<details>
  <summary>📌 Source</summary>
 
```power BI
= Csv.Document(File.Contents("C:\Users\admin\Downloads\Orders.csv"),[Delimiter=",", Columns=20, Encoding=65001, QuoteStyle=QuoteStyle.None])
```
Promote header

```power BI
= Table.PromoteHeaders(Source, [PromoteAllScalars=true])
```

change type
```power BI
= Table.TransformColumnTypes(#"Promoted Headers",{{"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Profit", type number}})
```

</details>

<details>
  <summary>📌 Returns</summary>
 
Source

```power BI
= Csv.Document(File.Contents("C:\Users\admin\Downloads\Returns.csv"),[Delimiter=",", Columns=2, Encoding=1252, QuoteStyle=QuoteStyle.None])
```

Changed Type

```power BI
= Table.TransformColumnTypes(Source,{{"Column1", type text}, {"Column2", type text}})
```

Promote Headers

```power BI
= Table.PromoteHeaders(#"Changed Type", [PromoteAllScalars=true])
```

Change type 1
```power BI
= Table.TransformColumnTypes(#"Promoted Headers",{{"Returned", type text}, {"Order ID", type text}})
```

Sorted Rows

```power BI
= Table.Sort(#"Changed Type1",{{"Order ID", Order.Ascending}})
```

Change type 2
```power BI
= Table.TransformColumnTypes(#"Sorted Rows",{{"Returned", type text}})
```

Trimmed Text
```power BI
= Table.TransformColumns(#"Changed Type2",{{"Order ID", Text.Trim, type text}})
```

Cleaned Text
```power BI
= Table.TransformColumns(#"Trimmed Text",{{"Order ID", Text.Clean, type text}})
```

</details>


<details>
  <summary>📌 Dim_employee</summary>
 
Sources
```power BI
= Csv.Document(File.Contents("C:\Users\admin\Downloads\People.csv"),[Delimiter=",", Columns=2, Encoding=1252, QuoteStyle=QuoteStyle.None])
```

Changed Type
```power BI
= Table.TransformColumnTypes(Source,{{"Column1", type text}, {"Column2", type text}})
```

Promoted Headers

</details>


<details>
  <summary>📌 Dim_location</summary>
 
Sources
```power BI
= Csv.Document(File.Contents("C:\Users\admin\Downloads\Orders.csv"),[Delimiter=",", Columns=20, Encoding=65001, QuoteStyle=QuoteStyle.None])
```

Promoted Headers

```power BI
= Table.PromoteHeaders(Source, [PromoteAllScalars=true])
```

Changed Type
```power BI
= Table.TransformColumnTypes(#"Promoted Headers",{{"Order ID", type text}, {"Order Date", type date}, {"Ship Date", type date}, {"Ship Mode", type text}, {"Customer ID", type text}, {"Customer Name", type text}, {"Segment", type text}, {"City", type text}, {"State", type text}, {"Country", type text}, {"Postal Code", Int64.Type}, {"Market", type text}, {"Region", type text}, {"Product ID", type text}, {"Category", type text}, {"Sub-Category", type text}, {"Product Name", type text}, {"Sales", type number}, {"Quantity", Int64.Type}, {"Profit", type number}})
```


</details>









2️⃣ Exploratory Data Analysis (EDA)  


<details>
  <summary>📌 Dim_employee</summary>
 
Sources
```power BI
= Csv.Document(File.Contents("C:\Users\admin\Downloads\People.csv"),[Delimiter=",", Columns=2, Encoding=1252, QuoteStyle=QuoteStyle.None])
```

Changed Type
```power BI
= Table.TransformColumnTypes(Source,{{"Column1", type text}, {"Column2", type text}})
```

Promoted Headers

</details>

orders
removed columns
```power BI
= Table.RemoveColumns(#"Changed Type",{"State", "Country", "Region", "Category", "Sub-Category", "Product Name", "Customer Name", "Segment"})
```

Trimmed text
```power BI
= Table.TransformColumns(#"Removed Columns",{{"Order ID", Text.Trim, type text}})
```

cleaned text
```power BI
= Table.TransformColumns(#"Trimmed Text",{{"Order ID", Text.Clean, type text}})
```

Merged queries
```power BI
= Table.NestedJoin(#"Cleaned Text", {"Order ID"}, Returns, {"Order ID"}, "Returns", JoinKind.LeftOuter)
```

Renamed Columns
```power BI
= Table.RenameColumns(#"Merged Queries",{{"Returns", "Return label"}})
```

Expanded Return Label
```power BI
= Table.ExpandTableColumn(#"Renamed Columns", "Return label", {"Returned"}, {"Return label.Returned"})
```

Renamed Columns1
```power BI
= Table.RenameColumns(#"Expanded Return label",{{"Return label.Returned", "Return label"}})
```
Replaced Value
```power BI
= Table.ReplaceValue(#"Renamed Columns1",null,"No",Replacer.ReplaceValue,{"Return label"})
```


<details>
  <summary>📌 Dim_location</summary>
 
Remove other columns
```power BI
= Table.SelectColumns(#"Changed Type",{"City", "State", "Country", "Market", "Region"})
```

Remove Columns
```power BI
= Table.RemoveColumns(#"Removed Other Columns",{"Market"})
```

Remove Duplicates

```power BI
= Table.Distinct(#"Removed Columns", {"City"})
```
Remove duplicate1
```power BI
= Table.Distinct(#"Removed Duplicates", {"City"})
```

Sort rows
```power BI
= Table.Sort(#"Removed Duplicates1",{{"City", Order.Ascending}})
```

</details>
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


#### 3️⃣ Dashboard 3: Sales by location  

![image](https://github.com/user-attachments/assets/16e29668-3235-49c0-ab9b-7e6432760433)
 

📌 Analysis 3:  
- Observation: _Describe trends, key metrics, and patterns._  
- Recommendation: _Suggest actions based on insights._

- United States là thị trường bán được nhiều đơn hàng nhất, đặc biệt là ở New York city 
Tại NYC thì các mặt hàng Technology, đặc biệt là phone bán chạy nhất. NYC cũng có tỷ lệ trả hàng thấp hơn trung bình => thị trường cần đẩy mạnh
Seattle có profit cao thứ 2 sau NYC, lĩnh vực có profit cao nhất cũng là technology, nhưng phần lớn đến từ copier, phone chỉ chiếm số ít
Sydney - Australia cũng có doanh số cao. Mặt hàng có profit cao nhất ở đây là Bookcase.
San Francisco là thành phố duy nhất trong top 5 profit có Office supplies chiếm tỷ lệ trong profit cao nhất, trong đó nhiều nhất là Art, sau đó là Label và envelopes

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
