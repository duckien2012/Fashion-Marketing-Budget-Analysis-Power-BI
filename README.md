# 📊 Fashion Marketing & Budget Analysis | Power BI

**Author:** Hoàng Đức Kiên 
**Date:** 2025
**Tools Used:** Power BI

---

## 📑 Table of Contents  
1. [📌 Background & Overview](#-background--overview)  
2. [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
3. [🧠 Design Thinking Process](#-design-thinking-process)  
4. [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
5. [🔎 Final Conclusion & Recommendations](#-final-conclusion--recommendations)

---

## 📌 Background & Overview  

### 📖 What is this project about?  

**Fashion Marketing & Sales Analysis** covers a fashion retail & e-commerce company selling seasonal apparel and lifestyle products across online and offline channels, where growth is driven by multi-channel marketing campaigns and revenue is closely tied to SKU-level campaign efficiency.

This project develops an interactive Power BI dashboard using internal campaign and sales data (Orders, Marketing Spend, SKU-level Ads) to transform raw transactional records into executive-level insights — bridging Marketing Investment and Sales Outcomes from overall budget health down to SKU-level ROAS.

The dashboard enables leadership to:

- ✔️ Monitor the overall financial health: Total Spend, Total Revenue, and Return on Ad Spend (ROAS).
- ✔️ Analyze individual campaign performance and identify bottlenecks in the Marketing Funnel.
- ✔️ Evaluate marketing ROI at the most granular level (Product/SKU level).
- ✔️ Optimize budget allocation based on KPIs and propose tactical improvements.

### 👤 Who is this project for?  

This dashboard is designed for:

- ✔️ **Executive leadership team** (C-level, Directors)   
- ✔️ **Marketing and Sales teams** 
- ✔️ **Data Analysts & Business Analysts** 
---

## 📂 Dataset Description & Data Structure
### 📌 Data Source  

- **Source:** Internal Marketing & Sales Data
- **Size:** ~3500+ rows
- **Format:** xlxs

#### **Tables used in the Dataset:**
<details>
<summary><strong>Table 1: mkt_camp_by_sku_cost - SKU-level marketing spend and ad performance data</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Tên chiến dịch | VARCHAR | Name of the marketing campaign. |
| Ngày | DATE | Date when campaign performance was recorded. |
| Đơn vị tiền tệ | VARCHAR | Currency used for campaign spending (e.g., VND). |
| Số tiền đã chi tiêu (VND) | DECIMAL | Total amount spent on the campaign for the given date. |
| Phân phối chiến dịch | VARCHAR | Campaign delivery status or distribution type. |
| Ngân sách chiến dịch | DECIMAL | Total budget allocated to the campaign. |
| Loại ngân sách chiến dịch | VARCHAR | Budget type (daily, lifetime, etc.). |
| Lần bắt đầu cuộc trò chuyện qua tin nhắn | INT | Number of initiated conversations via messaging. |
| Bình luận về bài viết | INT | Number of comments generated on the advertisement. |
| CPM | DECIMAL | Cost per 1,000 impressions. |
| CPC | DECIMAL | Cost per click. |
| CTR | DECIMAL | Click-through rate (clicks divided by impressions). |
| Tin nhắn mới | INT | Number of new incoming messages generated. |
| Lượt hiển thị | INT | Total number of ad impressions. |
| Mã Sản phẩm | VARCHAR | Unique product identifier (SKU). |
| Tên Sản Phẩm | VARCHAR | Product name. |
| Giá bán | DECIMAL | Selling price of the product. |
| Tên Bài Chạy | VARCHAR | Name of the running advertisement. |
| Bài chạy theo ngày | VARCHAR | Daily ad execution details. |
| Tiền đã chạy Theo Sản phẩm | DECIMAL | Marketing cost allocated to each specific product. |
| Ngân sách | DECIMAL | Budget allocated corresponding to the product or campaign. |

</details>

<details>
<summary><strong>Table 2: mkt_camp_cost - campaign-level budget and advertising efficiency metrics</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Tên chiến dịch | VARCHAR | Name of the marketing campaign. |
| Ngày | DATE | Date when campaign cost data was recorded. |
| Số tiền đã chi tiêu | DECIMAL | Total marketing expenditure for the campaign. |
| Phân phối chiến dịch | VARCHAR | Campaign delivery status or distribution type. |
| Ngân sách chiến dịch | DECIMAL | Total allocated campaign budget. |
| Loại ngân sách chiến dịch | VARCHAR | Type of campaign budget (daily, lifetime, etc.). |
| CPM (Chi phí trên mỗi 1.000 lần hiển thị) | DECIMAL | Average cost per 1,000 impressions. |
| CPC (Chi phí trên mỗi lượt click vào liên kết) | DECIMAL | Average cost per click on the advertisement link. |
| Lượt hiển thị | INT | Total number of impressions generated. |
| Click | INT | Total number of clicks generated. |

</details>

<details>
<summary><strong>Table 3: order - detailed transaction, product, and customer information</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| ID | VARCHAR | Unique order identifier. |
| Thời gian | DATETIME | Timestamp when the order was created. |
| Nguồn | VARCHAR | Sales channel or order source. |
| Tên khách hàng | VARCHAR | Customer full name. |
| Mã khách hàng | VARCHAR | Unique customer identifier. |
| Cấp độ khách hàng | VARCHAR | Customer tier or segmentation level. |
| Sinh nhật | DATE | Customer date of birth. |
| Thành phố | VARCHAR | Customer city. |
| Quận huyện | VARCHAR | Customer district. |
| Phường xã | VARCHAR | Customer ward. |
| Sản phẩm | VARCHAR | Name of the product sold. |
| Mã sản phẩm cha | VARCHAR | Parent product identifier. |
| Tên sản phẩm cha | VARCHAR | Parent product name. |
| Mã sản phẩm | VARCHAR | Product SKU code. |
| Mã vạch | VARCHAR | Product barcode. |
| Danh mục sản phẩm | VARCHAR | Product category. |
| Chiết khấu | DECIMAL | Discount applied to the product. |
| Giá | DECIMAL | Selling price per unit. |
| Số lượng | INT | Quantity sold. |
| Giá vốn | DECIMAL | Cost of goods sold per unit. |
| Trạng thái | VARCHAR | Order status (completed, canceled, etc.). |
| Lý do hủy | VARCHAR | Reason for cancellation (if applicable). |

</details>

<details>
<summary><strong>Table 4: danh sach san pham - master product catalog for pricing and inventory analysis</strong></summary>

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| ID | VARCHAR | Unique product identifier. |
| Mã vạch | VARCHAR | Product barcode. |
| Loại sản phẩm | VARCHAR | Product type classification. |
| Mã sản phẩm | VARCHAR | Product SKU code. |
| Tên sản phẩm | VARCHAR | Product name. |
| Giá nhập | DECIMAL | Purchase/import price of the product. |
| Giá bán | DECIMAL | Standard selling price. |
| Giá bán + VAT | DECIMAL | Selling price including VAT. |
| Giá vốn | DECIMAL | Cost of goods sold. |
| Trạng thái | VARCHAR | Product status (active, inactive, etc.). |
| Mã danh mục | VARCHAR | Product category code. |
| Danh mục | VARCHAR | Product category name. |
| Mã danh mục nội bộ | VARCHAR | Internal category identifier. |
| Thương hiệu | VARCHAR | Product brand. |
| Màu sắc | VARCHAR | Product color. |
| Chất liệu | VARCHAR | Product material. |
| Theo sản phẩm | VARCHAR | Allocation or performance indicator by product. |
| Inbox Theo AM | INT | Number of inbox messages recorded by AM. |
| Comments Theo AM | INT | Number of comments recorded by AM. |
| Inbox + Comments Theo AM | INT | Total engagement (inbox + comments) recorded by AM. |
| CP/KQ Theo AM | DECIMAL | Cost per result recorded by AM. |
| CPM Theo AM | DECIMAL | Cost per 1,000 impressions recorded by AM. |
| CPC Theo AM | DECIMAL | Cost per click recorded by AM. |
| CTR Theo AM | DECIMAL | Click-through rate recorded by AM. |
| Khách mới Theo AM | INT | Number of new customers acquired by AM. |
| Khách cũ Theo AM | INT | Number of returning customers by AM. |
| Lượt hiển thị Theo AM | INT | Total impressions recorded by AM. |
| SL bán tổng | INT | Total quantity sold. |
| Tổng CMT trên SP | INT | Total comments on the product. |
| SL bán được phân bổ theo tỉ lệ | INT | Quantity sold allocated proportionally. |
| SL tồn | INT | Remaining inventory quantity. |
| Tổng SL bán theo Campaign | INT | Total quantity sold attributed to campaign. |

</details>

### 📊 Data Structure & Relationships After Data Modeling

#### 1️⃣ Tables in Schema

The project uses a **galaxy schema** model consisting of:

- **2 Fact Tables:** `Fact_Orders` (Sales data), `Fact_mkt_camp_by_sku` (Allocated costs at the SKU level).
- **4 Dimension Tables:** `Dim_mkt_camp_cost`, `Dim_Customers`, `Dim_Product`, `Dim_Date`.

#### 2️⃣ Table Schema & Data Snapshot  

<details>
<summary> <strong>🧾 Fact_Orders: transactional data about orders</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| ID | Text | Unique order identifier |
| Thời gian | DateTime | Order creation timestamp |
| Mã khách hàng | Text | Foreign key to Dim_Customers |
| Mã sản phẩm | Text | Foreign key to Dim_Product |
| Mã vạch | Text | Barcode used for product-level joins |
| Giá | Decimal | Selling price per unit |
| Số lượng | Integer | Units sold |
| Giá vốn | Decimal | Cost of goods sold per unit |
| Chiết khấu | Decimal | Discount applied to the order line |
| Nguồn | Text | Sales channel or order source |
| Trạng thái | Text | Order status |
| Lý do hủy | Text | Cancellation reason, if applicable |
</details>

<details>
<summary> <strong>📢 Fact_mkt_camp_by_sku: SKU-level campaign spend and ad performance data</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| Campaign ID | Text | Unique campaign identifier |
| Tên chiến dịch | Text | Campaign name |
| Ngày | Date | Campaign reporting date |
| Mã Sản phẩm | Text | Foreign key to Dim_Product |
| Tên Sản Phẩm | Text | Product name linked to the campaign |
| Số tiền đã chi tiêu (VND) | Decimal | Total ad spend recorded |
| Ngân sách chiến dịch | Decimal | Budget allocated to the campaign |
| Tiền đã chạy Theo Sản phẩm | Decimal | Spend allocated to each SKU |
| Lượt hiển thị | Integer | Total ad impressions |
| Click | Integer | Total clicks generated |
| CPC | Decimal | Cost per click |
| CPM | Decimal | Cost per 1,000 impressions |
| CTR | Decimal | Click-through rate |
| Lần bắt đầu cuộc trò chuyện qua tin nhắn | Integer | Messaging conversations initiated |
| Bình luận về bài viết | Integer | Comments generated from the ad |
</details>

<details>
<summary> <strong>📊 Dim_mkt_camp_cost: campaign-level budget and advertising efficiency metrics</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| Campaign ID | Text | Unique campaign identifier |
| Tên chiến dịch | Text | Campaign name |
| Ngày | Date | Campaign reporting date |
| Số tiền đã chi tiêu | Decimal | Total marketing spend recorded for the campaign |
| Ngân sách chiến dịch | Decimal | Total budget allocated to the campaign |
| Loại ngân sách chiến dịch | Text | Budget type such as daily or lifetime |
| Phân phối chiến dịch | Text | Campaign delivery status |
| Lượt hiển thị | Integer | Total ad impressions |
| Click | Integer | Total clicks generated |
| CPC (Chi phí trên mỗi lượt click vào liên kết) | Decimal | Average cost per click |
| CPM (Chi phí trên mỗi 1.000 lần hiển thị) | Decimal | Average cost per 1,000 impressions |
</details>

<details>
<summary> <strong>👥 Dim_Customers: customer master data for segmentation and geography</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| Mã khách hàng | Text | Unique customer identifier |
| Tên khách hàng | Text | Customer full name |
| Cấp độ khách hàng | Text | Customer tier or segment |
| Sinh nhật | Date | Customer date of birth |
| Thành phố | Text | Customer city |
| Quận huyện | Text | Customer district |
| Phường xã | Text | Customer ward |
</details>

<details>
<summary> <strong>👗 Dim_Product: product master data for category, pricing, and attributes</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| ID | Text | Unique product record identifier |
| Mã sản phẩm | Text | Business product or SKU code |
| Mã vạch | Text | Product barcode |
| Tên sản phẩm | Text | Product name |
| Loại sản phẩm | Text | Product type classification |
| Danh mục | Text | Product category |
| Mã danh mục | Text | Category identifier |
| Mã danh mục nội bộ | Text | Internal category code |
| Thương hiệu | Text | Brand name |
| Chất liệu | Text | Product material |
| Màu sắc | Text | Product color |
| Giá nhập | Decimal | Purchase or import price |
| Giá vốn | Decimal | Cost of goods sold |
| Giá bán | Decimal | Standard selling price |
| Giá bán + VAT | Decimal | Selling price including VAT |
| Trạng thái | Text | Product status |
</details>

<details>
<summary> <strong>📅 Dim_Date: calendar table for time-based reporting</strong></summary>

| Column Name | Data Type | Description |
|------------|-----------|-------------|
| Date | Date | Primary date key used to connect fact tables |
| Date_Report | Date | Reporting date used for campaign tracking |
| Day | Integer | Day number within the month |
| Day Short | Text | Abbreviated weekday name |
| Day Short VN | Text | Vietnamese abbreviated weekday name |
</details>

#### 3️⃣ Data Relationships 
![Data Model](https://github.com/user-attachments/assets/565d3b93-c3ba-4a38-87b9-d0a55336789f)

---

## 🧠 Design Thinking Process 

### 1️⃣ Empathize  
![5W1H Table](https://github.com/user-attachments/assets/b82349da-6ca8-473c-b0da-347b13a441b5)
![Empathy Map](https://github.com/user-attachments/assets/0bf45418-9e67-40f1-83c8-4f3f81db5cc9)

---

### 2️⃣ Define Point of View 
![Stakeholders Journey](https://github.com/user-attachments/assets/fe0c9063-8378-4be4-aac6-f48a95413d7c)
![Stage2](https://github.com/user-attachments/assets/1e39d486-6520-4fcf-97d7-c51081b75180)
<!-- ![Stakeholders Journey](https://github.com/user-attachments/assets/fe0c9063-8378-4be4-aac6-f48a95413d7c)
![Northstar Metrics](https://github.com/user-attachments/assets/7cffb78c-d941-4fad-aa9a-7905b715178c)
![POV and Business Views](https://github.com/user-attachments/assets/126514ad-ced6-4d40-bb73-0a7fe66664b7) -->

---

### 3️⃣ Ideate  
![Structure Idea](https://github.com/user-attachments/assets/90d51fee-d053-4e14-8669-efba6643ad13)
![Visualization Idea](https://github.com/user-attachments/assets/e1e9fa4f-0bcd-4e8a-bd32-9229b600b1fa)

---

### 4️⃣ Prototype & Review  
This phase is implemented and validated directly within the interactive dashboard.

---

## 📊 Key Insights & Visualizations  

### 📌 Dashboard 1: Executive Overview

![Executive Overview](https://github.com/user-attachments/assets/2b8fae0c-b146-4a6f-9714-ae05888fae26)
**Key Findings:**

- **Overall KPIs:** 
    - The dashboard shows Revenue Ads at **$3.02bn**, Total Spend at **$394.13M**, ROAS at **7.67**, Overall CR at **0.14%**, and Total Orders at **2858**.

- **Marketing Overview by Time:** 
    - Revenue Ads and Total Spend (bars) reach their highest volume in **Week 3 and Week 4** (approaching $0.8bn), but the ROAS (orange line) peaks later in **Week 5** at nearly **9.0**.
    - This means ad efficiency actually improves toward the end of the month even when absolute spending decreases, suggesting the campaigns optimize better over time or target a highly intent-driven audience late in the month.

- **Revenue Ads/Direct Sales:** 
    - **Direct Sales** (dark blue) account for **63.34%** ($3.02bn) of the pie, while **Ads Sales** (light blue) account for **36.66%** ($1.75bn). 
    - This means the business has a very healthy organic baseline and strong customer retention (Direct Sales), reducing total dependency on paid advertising for survival.

- **Ad Spend vs. Budget:** 
    - The total ad spend is **394.13M** against a target of **788.26M**, but the gauge displays a completion rate of **82.75%**.
    - This means the ad pacing is extremely aggressive. The campaigns are burning through the allocated budget much faster than anticipated and require immediate pacing adjustments.

- **Total Orders by Week and Ads/Direct:** 
    - Both Ads Sales and Direct Sales orders peak in **Week 4** (511 and 280 orders) and drop sharply in **Week 5** (421 and 242 orders).
    - This means there is a predictable end-of-month slump in purchasing volume across all channels, likely due to consumer salary cycles.

- **Total Revenue by Product List and Ads/Direct:** 
    - **"Váy Chiết Eo Xòe"** leads with **$1.49bn**, heavily supported by Direct Sales, followed by **"Áo Tách Set"** at **$1.05bn**. Bottom items like "Áo Khoác" generate near **$0.00**.
    - This means "Váy Chiết Eo Xòe" is the ultimate Hero Product. The stark contrast between the top and bottom products indicates a highly skewed product portfolio where only a few items drive the majority of cash flow.

- **ROAS and Spend vs Budget by Week and Day:** 
    - The trendline shows a negative correlation: campaigns with the highest Spend tend to cluster around a lower ROAS (**5-10**), while low-spend dots occasionally hit ROAS levels of **>20**.
    - This means scaling up the budget currently leads to diminishing returns. As campaigns spend more, their capital efficiency drops.

---

### 📢 Dashboard 2: Campaign Analysis
![Campaign Analysis](https://github.com/user-attachments/assets/11d5e605-c83f-49c0-9742-8553ff706117)

**Key Findings:**

- **KPI Cards:** 
    - Across **854** total campaigns, the average CPC is **9.46K**, CPM is **77.14K**, and CTR is **0.82%**.

- **Weekly Ad Performance:** 
    - The CTR (orange line) dips to its lowest in **Week 2** before spiking to nearly **1.0%** in **Week 3**, which inversely mirrors the high CPM/CPC costs during Week 2.
    - This means ad creatives experienced ad fatigue or poor targeting in Week 2, but adjustments made in Week 3 successfully captured audience interest and lowered click costs.

- **Marketing Funnel:** 
    - **Impressions** (5,108.97K) convert to **Clicks** (41.65K), generating **11.44K** Inbox/Comments. However, only **1.96K** convert to **Ads Orders**.
    - This means the ads are doing a great job at generating cheap leads, but there is a massive operational failure at the bottom of the funnel. A closing rate of roughly **17%** from engaged conversations indicates weak telesales/chatbot performance.

- **Budget vs Spend by Product List:** 
    - **"Chân Váy Tách Set"** and **"Áo Tách Set"** have the highest budget consumption rates at **89.37%** and **86.68%**.
    - This means the budgets for these top-performing product groups are nearly exhausted and need immediate top-ups to maintain momentum.

- **Top 5 Campaign by ROAS:** 
    - The campaign **"KINO DRESS - ib - Re - 1000k"** achieves an extraordinary ROAS of **101.63**.
    - This means remarketing (Re) campaigns with specific high-value offers (1000k) for this specific dress are incredibly lucrative and should be duplicated as a template.

- **Bottom 5 Campaign by ROAS:** 
    - Campaigns like **"Story 31.5 - ib - Op"** and **"CAMY DRESS"** register a flat ROAS of **0.00**.
    - This means these campaigns are "dead weight" that are actively burning cash without generating a single order and must be paused immediately.
---

### 📦 Dashboard 3: Product Analysis

![Product Analysis](https://github.com/user-attachments/assets/3e299685-2104-456e-8edf-382ffa65aa9c)

**Key Findings:**

- **KPI Cards:** 
    - Ads specifically drove **1958** Orders with a ROAS of **7.67**.

- **Weekly Ad Performance - Revenue vs ROAS:** 
    - **"Váy Chiết Eo Xòe"** has the highest absolute ad revenue (tallest bar, ~$1.0bn), but **"Set Váy Áo"** creates a towering spike in the ROAS line graph (reaching approx **15-20**).
    - This means "Set Váy Áo" is the "hidden gem" of the portfolio. It requires very little ad spend to sell out, making it the most profitable item to scale up.

- **Weekly Ad Performance by Category:** 
    - **"Quần Tách Set"** sits in the top left quadrant with high CTR (~1%) but very low CPC.
    - This means there is massive organic interest and curiosity for this item, generating extremely cheap traffic that should be capitalized on with strong landing page offers.

- **Top 5 Product by Revenue Ads:** 
    - **"Audrey Shirt 3"** is the best-performing individual SKU, bringing in **$0.31bn** in Ad Revenue alone.
    - This means this specific shirt variant resonates perfectly with the online audience and should be featured as the primary thumbnail in carousel ads.

- **Bottom 5 Product by Revenue Ads:** 
    - Items like **"Lana Dress"**, **"Aleica Dress 2"**, and **"Alicia Set"** sit at exactly **$0.00** Ad Revenue.
    - This means these are failed SKUs in the digital space. They are eating up warehouse space and ad testing budgets and should be liquidated offline or bundled.

---

## 🔎 Final Conclusion & Recommendations  

👉🏻 Based on the insights extracted from all three levels (Executive, Campaign, Product), the analytics team proposes the following tactical actions for the Senior Leadership:

| Strategy | Insight | Recommendation |
|-----------|----------|----------------|
| 🚀 **1. Marketing Efficiency & Pacing** | - The overall strategy is highly profitable. <br>- Organic revenue (Direct Sales) dominates, creating a solid foundation and reducing the pressure on paid Ads. <br>- There is a clear, cyclical sales drop in the final week of the month. <br>- The budget "burn rate" is too aggressive compared to the timeline. | - Reset budget pacing to prevent budget depletion by month-end.<br>- Run Flash Sales or Promo campaigns in the last week to counter the cyclical drop-off.<br>- Continue to strengthen customer retention programs (Direct Sales). |
| 🎯 **2. Campaign Portfolio Optimization** | - Extreme performance polarization: Top campaigns yield massive profit margins, while the Bottom group simply burns cash. <br>- Remarketing campaigns with specific offers (e.g., discounts/gifts) perform the best. <br>- Broad-scale spending on generic formats (like general Reels) delivers very poor conversion rates. | - Immediately cut/pause the cash-burning (Bottom) campaigns.<br>- Use successful Remarketing campaigns as templates to duplicate and scale.<br>- Stop using Conversion-objective budgets for broad, entertainment-focused videos. |
| 🛍 **3. Product & SKU Strategy** | - The product portfolio is highly skewed: A few "Hero Products" carry the vast majority of the revenue. <br>- The highest revenue-generating product is not always the most cost-efficient for Ads (some low-spend SKUs yield incredibly high returns). <br>- There is a group of "dead weight" SKUs generating zero Ad revenue. | - Use "Hero Products" as loss leaders/bait to drive cheap traffic to the store. <br>- Aggressively scale Ad budgets for the SKUs/Sets with the sharpest ROAS trendlines to maximize net profit. <br>- Liquidate or bundle "dead" SKUs to cut warehousing costs. |
| 🔁 **4. Funnel & Conversion Optimization** | - Ads excel at Top-of-Funnel awareness and generate an abundant, cheap supply of leads (Inbox messages). <br>- The critical bottleneck is at the Bottom-of-Funnel: The ratio of customers who message to those who actually buy is extremely low. <br>- Ad content shows signs of fatigue mid-month but recovers well upon optimization. | - Conduct a full audit of Telesale/Chatbot closing scripts and shipping fee policies. <br>- Launch Retargeting campaigns with exclusive Vouchers aimed specifically at the "Inboxed but didn't buy" audience. <br>- Regularly rotate ad creatives (images/videos) to prevent ad fatigue. |
| 💰 **5. Budget Allocation & Capital Efficiency** | - Scaling up is showing diminishing returns: Pumping more money into a single campaign tends to lower its profit margin. <br>- Misaligned budget allocation: Over-investing in highly competitive niches (steady volume but low margins) while starving specialized niches (low costs, high margins). | - Shift cash flow away from the highly competitive "Work/Play" category and into the highly profitable "Party" niche. <br>- Establish a strict CPA (Cost Per Acquisition) ceiling for each category. <br>- Instead of increasing the budget of an existing ad, duplicate it to target a fresh audience pool. |