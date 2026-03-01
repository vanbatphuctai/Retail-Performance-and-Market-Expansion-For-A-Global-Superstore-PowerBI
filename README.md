# 📊 Retail Performance & Market Expansion For A Global Superstore | Power BI

**Author:** Van Bat Phuc Tai  
**Tools Used:** Power BI

---

## 📑 Table of Contents
- [📌 Background & Overview](#-background--overview)  
- [📂 Dataset Description & Data Structure](#-dataset-description--data-structure)  
- [🧠 Design Thinking Process](#-design-thinking-process)  
- [📊 Key Insights & Visualizations](#-key-insights--visualizations)  
- [🔎 Final Conclusion & Recommendation](#-final-conclusion--recommendation)  

---

## 📌 Background & Overview  

### 🎯 Objective  

Developed a **Power BI dashboard** using the Global Superstore dataset (Orders, People, Returns) to transform transactional data into **actionable business insights** for strategic decision-making.  

The project focuses on:  

- Evaluating overall **sales and profitability performance**  
- Identifying **high-potential markets for expansion**  
- Prioritizing **profitable and scalable product categories**  
- Supporting **ROI-driven decision-making**  

---

### 👤 Target Users  

- Data Analysts & Business Analysts  
- Sales & Marketing teams  
- Route-to-Market & Strategy teams  

---

### ❓ Key Business Questions  

- What is the current performance baseline?  
- Which markets show the strongest growth and ROI potential?  
- Which products should be prioritized for strategic investment?  

---

### 🎯 Project Outcome  

Revenue scaled steadily, but **margin expansion remained constrained**, indicating operational cost pressure.  

Several regions demonstrated **strong margin quality and growth momentum**, highlighting expansion opportunities.  

Technology led revenue performance, though **return-heavy SKUs impacted profitability**. High-margin categories outperformed, while weaker segments diluted overall results.  

This analysis supports alignment between **market expansion strategy, product portfolio optimization, and profitability improvement**.  

---

## 📂 Dataset Description & Data Structure  

### 📌 Data Source  

- Source: Kaggle  
- Format: CSV  
- ~51K transaction records (Orders table)  

### 📊 Data Structure  

### 1️⃣ Tables Used:

The dataset consists of three relational tables:  

🛒 Orders – Contains detailed transaction and customer information (51,290 records).

<details>
<summary><strong>Table 1: Orders</strong></summary>

| Column Name   | Data Type | Description |
|--------------|----------|------------|
| Order ID     | VARCHAR  | Unique identifier for each order. |
| Order Date   | DATE     | Date when the order was placed. |
| Ship Date    | DATE     | Date when the order was shipped. |
| Ship Mode    | VARCHAR  | Shipping method used for delivery. |
| Customer ID  | VARCHAR  | Unique identifier for each customer. |
| Customer Name| VARCHAR  | Full name of the customer. |
| Segment      | VARCHAR  | Customer segment (e.g., Consumer, Corporate). |
| City         | VARCHAR  | City where the order was placed. |
| State        | VARCHAR  | State where the order was placed. |
| Country      | VARCHAR  | Country where the order was placed. |
| Postal Code  | VARCHAR  | Postal code of the shipping address. |
| Market       | VARCHAR  | Market region (e.g., APAC, EMEA). |
| Region       | VARCHAR  | Geographical region of the order. |
| Product ID   | VARCHAR  | Unique identifier for each product. |
| Category     | VARCHAR  | Product category (e.g., Furniture, Office Supplies). |
| Sub-Category | VARCHAR  | Sub-category of the product. |
| Product Name | VARCHAR  | Name of the product ordered. |
| Sales        | DECIMAL  | Revenue generated from the order. |
| Quantity     | INT      | Number of items ordered. |
| Profit       | DECIMAL  | Profit earned from the order. |

</details>

🔄 Returns – Stores data on returned orders.

<details>
<summary><strong>Table 2: Returns</strong></summary>

| Column Name | Data Type | Description |
|-------------|----------|------------|
| Returned    | VARCHAR  | Indicates whether the order was returned (e.g., 'Yes' or 'No'). |
| Order ID    | VARCHAR  | Unique identifier for each order. |

</details>

👥 People – Holds information about sales representatives.

<details>
<summary><strong>Table 3: People</strong></summary>

> 👥 Holds information about sales representatives.

| Column Name | Data Type | Description |
|-------------|----------|------------|
| Person      | VARCHAR  | Name of the salesperson. |
| Region      | VARCHAR  | Geographic region where the salesperson operates. |

</details>

### 2️⃣ Data Relationships:

<img width="1380" height="800" alt="image" src="https://github.com/user-attachments/assets/c21503b1-f855-48f0-8833-2f67b4aa0257" />

### 🔗 Data Model Relationships

| From Table     | To Table        | Join Key        | Relationship Type |
|---------------|----------------|----------------|-------------------|
| Fact_Orders   | Dim_Product    | Product ID     | Many-to-One (*:1) |
| Fact_Orders   | Dim_Customer   | Customer ID    | Many-to-One (*:1) |
| Fact_Orders   | Dim_Date       | Order Date     | Many-to-One (*:1) |
| Fact_Orders   | Dim_Location   | Location ID    | Many-to-One (*:1) |
| Fact_Orders   | Dim_Market     | Market ID      | Many-to-One (*:1) |
| Fact_Orders   | Dim_Ship_Mode  | Ship Mode ID   | Many-to-One (*:1) |
| Fact_Orders   | Dim_Segment    | Segment ID     | Many-to-One (*:1) |
| Fact_Orders   | Dim_Returns    | Order ID       | Many-to-One (*:1) | 
| Dim_Product   | Dim_Subcategory| Subcategory ID | Many-to-One (*:1) |
| Dim_Subcategory | Dim_Category | Category ID    | Many-to-One (*:1) |
| Dim_Market    | Dim_People     | Region         | Many-to-One (*:1) |

## 🧠 Design Thinking Process

### 1️⃣ Empathize

### 🧠 STAGE 1: EMPATHIZE - 5W1H

| Who will view this Dashboard? | What problem does this dashboard solve? | When and where will stakeholders view this dashboard? | Why is this analysis needed? | How do stakeholders make decisions? |
|--------------------------------|------------------------------------------|--------------------------------------------------------|------------------------------|--------------------------------------|
| - Senior Manager <br> - Board of Directors (CEO, COO) <br> - Sales Director / Head of Sales <br> - Regional Sales Managers <br> - Marketing Manager <br> - Product Manager <br> - Finance Manager | - Overall business performance: revenue, profit, growth. <br> - Market performance: which regions are growing and which need improvement. <br> - Product performance: leading products and high-potential products. <br> - Customer trends: purchasing behavior, retention rate, order value. <br> - Risks & opportunities: declining markets, high return rates, rising costs. | **When:** <br> - Weekly / monthly performance tracking. <br> - Before investment or expansion decisions. <br> - After marketing campaigns or new product launches. <br><br> **Where:** <br> - Strategic meetings, periodic reports, executive presentations. <br> - On personal computers, tablets, or presentation screens. | - To support strategic market expansion decisions. <br> - To select key products for investment and development. <br> - To optimize product portfolio and sales channels. <br> - To present insights to executives or the board. | - Through interactive and easy-to-understand visuals (filters by market, product, time). <br> - Insight-focused, not overly technical. <br> - Using executive scorecards, trend charts, and regional/product comparisons. <br> - Exportable to PDF or presentation format. |
| **If only one key stakeholder is chosen, who would it be?** | **Summarize the problem in one sentence:** |  |  |  |
| Senior Sales Manager | Provide business data to support market expansion and strategic product selection. |  |  |  |

# 🧠 STAGE 1: EMPATHY MAP

| Thinking & Feeling <br><sub>What does the stakeholder think and feel?</sub> | Seeing <br><sub>What does the stakeholder see?</sub> | Saying & Doing <br><sub>What does the stakeholder say and do?</sub> |
|--------------------------------|--------------------------------|--------------------------------|
| - Concerned that wrong decisions may significantly impact the business. <br> - Wants data that is easy to understand and actionable. <br> - Feels pressure to make fast but accurate decisions. <br> - Lacks time to analyze excessive or complex information. <br> - Wants to control risks while still driving growth. | - Dense reports and multiple spreadsheets. <br> - Data scattered across departments. <br> - Increasing market competition. <br> - Market fluctuations. <br> - Rapid global economic changes. | - "I need an intuitive and easy-to-understand dashboard." <br> - "Can I trust this data?" <br> - Frequently requests quick reports and updates. <br> - Participates in strategy meetings and presents to executives. |
| **Pains** <br><sub>What are the biggest problems and challenges?</sub> | **STAKEHOLDER** | **Gains** <br><sub>What are the opportunities and benefits?</sub> |
| - Lack of an intuitive tool to consolidate data. <br> - Difficult to compare markets and products clearly. <br> - Data updates are not timely. <br> - No early warning system for risks. <br> - Sometimes decisions rely on intuition instead of data. | **Senior Sales Manager** | - Interactive and intuitive dashboard with real-time updates. <br> - Clear market and product insights. <br> - Data-driven strategic recommendations. <br> - Early risk detection capability. <br> - Greater confidence in data-driven decisions. |


### 2️⃣ Define Point of View


### 3️⃣ Ideate


### 4️⃣ Prototype and Review
This phase is implemented and validated directly within the interactive dashboard.

---

## 📊 Key Insights & Visualizations

### 🔍 Dashboard Preview

### I. Overview
