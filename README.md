📊 Retail Performance & Market Expansion For A Global Superstore | Power BI

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

### 🌍 Global Superstore Sales – Business Context

**Global Superstore** is a **multinational retail company** operating across multiple global markets.  
The company sells **Furniture, Office Supplies, and Technology** products through **regionally assigned sales representatives**.

---

### 🎯 Business Objective

Senior management requires a **clear view of overall business performance, market dynamics, and product category results** to define **market expansion strategy** and identify **strategic product priorities**.

The goal is to support **data-driven decision-making** that improves **revenue quality, profitability, and ROI** across markets and product categories.

---

### ❗ Why This Analysis Matters

To expand effectively, leadership must understand not only **revenue performance** but also **market-level** and **product-level contribution** to overall results.

Without **structured performance analysis**:

- **Market expansion decisions** may lack performance validation  
- **Strategic product selection** may not align with actual profitability  
- Growth efforts may overlook **performance gaps** across regions or categories  

This dashboard provides a **consolidated performance view** to support **data-driven expansion strategy** and **product prioritization decisions**.

---

### 👤 Target Users

- **Senior Management**  
- **Strategy & Expansion Teams**  
- **Sales & Marketing Teams**  
- **Data / Business Analysts**  

---

### ❓ Key Business Questions

- What is the **current business performance**?
- Which markets demonstrate **strong growth and sustainable profitability**?
- Which product categories drive **high-margin revenue**?
- Where are operational risks (**low margin, high return rate**) impacting results?

---

### 📊 Project Outcome

- Revenue increased steadily, but **margin expansion remained constrained** due to cost pressure.  
- Several markets showed **strong profitability and growth momentum** → expansion opportunities.  
- **Technology** led revenue contribution; however, **return-heavy SKUs reduced margin quality**.  
- **High-margin categories** outperformed, while weaker segments diluted overall profitability.  

This project enables alignment between **market expansion strategy, product portfolio optimization, and profitability improvement**.

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

## 🧠 Design Thinking Process

### 1️⃣ Empathize

<img width="1400" alt="image" src="https://github.com/user-attachments/assets/33898a50-0a23-4228-a3b0-2daedf47e13c" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/2da90e48-879e-4ffe-8b8f-373070697f7d" />


### 2️⃣ Define Point of View

<img width="1400" alt="image" src="https://github.com/user-attachments/assets/b537b0dd-3c3f-49b8-87bc-a5276669bc73" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/ce1e4e91-09ae-4743-9aae-0f292af04e39" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/21f0b09b-b1c2-4890-9253-fa8075b17fa5" />


### 3️⃣ Ideate

<img width="1400" alt="image" src="https://github.com/user-attachments/assets/c379ad21-c678-4aad-9540-b4fd3e37a429" />
<img width="1400" alt="image" src="https://github.com/user-attachments/assets/44945bfa-ccd4-486e-967b-b3ba3d62c990" />


### 4️⃣ Prototype and Review
This phase is implemented and validated directly within the interactive dashboard.

---

## 📊 Key Insights & Visualizations

### 🔍 Dashboard Preview

### I. Business Overview

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/e2a4dc9f-2b61-44d2-804d-329b18d7def9" />

### 📌 Key Findings:

#### 1. Total Revenue, Total Profit & Profit Margin  

Revenue reached **$12.64M (+51.5%)** and Profit hit **$1.47M (+52.3%)**, with Orders up **+51.7%**.  
→ Growth was strongly **volume-driven**, with revenue rising at the same pace as orders, suggesting **no meaningful change in AOV**, while margin slightly improved to **11.61%**.

#### 2. Business Performance Overview by Year  

Revenue & profit increased consistently (2011–2014).  
Profit margin peaked at **~11.95% (2013)** and remained stable.  
→ Indicates **sustainable scaling with controlled profitability**.

#### 3. Business Performance Overview by Market  

**APAC & EU** led total revenue.  
**Canada achieved the highest margin (~26.6%)** despite low revenue share.  
→ Large markets drive scale; **Canada shows strongest profitability potential**.

#### 4. Business Performance Overview by Category  

**Technology generated the highest revenue & strong margin (~14%)**.  
**Furniture recorded the lowest margin (~7%)**.  
→ Technology is the **core profit driver**.

#### 5. Trends in Order & Return Rate  

Orders grew steadily, while **Return Rate declined after 2012 (~4.6%)**.  
→ Growth occurred **without increasing operational risk**.

#### 6. Revenue Growth by Market/Category (YoY%)  

**EMEA (~59.8%) & Africa (~56.5%) showed the highest growth**.  
US grew slower (~47%) but remains a core base market.  
→ **Emerging markets are accelerating fastest**.

#### 7. Orders, Customers & Return Rate by Category  

**Office Supplies led order volume**.  
Return rates remained stable (~5–6%).  
→ Volume growth is **healthy and controlled**.


### II. Market Analysis

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/552a57e8-c730-4812-aeb9-58f0556448d1" />

### 📌 Key Findings:

#### 1. Revenue & Profit Overview 

Total Revenue reached **$12.64M** and Total Profit **$1.47M**.
APAC, EU, and US are the core revenue contributors, anchoring overall performance.  
Profitability, however, varies meaningfully across markets.
→ Scale is concentrated in major markets, but **margin structure differs** by region.

#### 2. Growth Dynamics (YoY)

EMEA (+59.8%) and Africa (+56.5%) recorded the fastest YoY growth, while US (+46.9%) expanded more moderately.
→ Growth momentum is shifting toward **emerging markets**, while mature markets remain stable revenue pillars.

#### 3. Market Efficiency Contrast

Core markets operate at healthy mid-level margins (~12–13%).  
Canada delivers the highest margin (~26.6%) despite limited scale, whereas EMEA runs at the lowest margin (~5.5%).
→ Clear divergence between **volume-driven** core markets and **margin-driven** niche markets.

#### 4. Sales Performance Concentration

Top salesperson generated ~$2.82M, significantly outperforming peers (~$0.88M–$1.60M).
→ Revenue concentration highlights a **capability gap** and **scalability opportunity** within the sales team.

### III. Product Analysis

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/a1975264-8e9c-4e8b-925d-0b22e2e59c86" />

### 📌 Key Findings:

#### 1. Revenue vs. Revenue LY & %YoY by Category  

**Technology** generated the highest revenue (**\~$4.8M**) and maintained strong **YoY growth (\~51–52%)**.  
**Office Supplies** showed the highest YoY growth (**\~52.6%**), while **Furniture** grew slower (**\~50.4%**).  
→ **Technology remains the core revenue engine**, with all categories sustaining **>50% growth**.

#### 2. Total Orders, Total Profit & Revenue by Sub-Category  

Sub-categories with **high orders and strong profit** cluster in the upper-right quadrant (e.g., **Copiers, Phones**).  
Some sub-categories show **high order volume but lower profit contribution**, indicating **margin pressure**.  
→ **Clear gap between volume-driven and profit-efficient sub-categories**.

#### 3. Impact of Shipping Mode on Return Volume  

**Standard Class** recorded the highest return volume (**677 returns**) but maintained a moderate **return rate (\~4.47%)**.  
**First Class** and **Same Day** showed slightly higher return rates (**\~5%**).  
→ **Faster shipping does not significantly reduce return risk**; **volume drives total returns**.


#### 4. Sales Metrics Overview (Revenue / Profit / Return Rate by Sub-Category & Region)  

**Binders, Furnishings, and Art** show strong revenue concentration in **US and EU markets**.  
Revenue distribution varies significantly across regions, with **US contributing the largest share** in most sub-categories.  
→ **Performance heavily depends on geographic demand concentration**.

#### 5. Top 10 Products by Revenue, Profit & Return Rate  

Top products (e.g., **Apple Smart Phone, Cisco Smart Phone, Motorola Smart Phone**) dominate revenue contribution (**\~$47K–$87K range**).  
**Technology products** account for the majority of top-ranking items.  
→ **Profit and revenue leadership is concentrated within Technology**, confirming **category dominance**.

### IV. Sales Agent 

<img width="1300" alt="image" src="https://github.com/user-attachments/assets/30dbd9e9-85e8-4e3e-b70b-06cfd40de3e7" />

### 📌 Key Findings

#### 1. Revenue & Profit Distribution by Sales Agent
**Anna Andreadi (US-West / Multi-US)** generated the highest **Revenue (~$2.82M)** but operated at a moderate **Margin (~11%)**, reflecting a **high-volume, competitive pricing model**.  
**Chuck Magee (US-South)** showed similar **revenue-driven performance** with mid-range margins.  

In contrast, **Nicole Hansen (Canada)** achieved the highest **Margin (~26.6%)** despite a smaller revenue base, while **Shirley Daniels (North Asia)** maintained a strong **Margin (~19.5%)** with steady growth momentum.  

→ **US agents = Revenue engines** | **Canada & North Asia = Profit efficiency leaders**

#### 2. Revenue Growth by Category Across Sales Agents
All agents sustained strong **YoY Growth (~50%+)**.  

High-margin agents (**Nicole Hansen, Shirley Daniels**) align strongly with **Technology (Phones, Copiers)**.  
High-volume US agents maintain broader exposure, including **lower-margin Furniture**.  

→ **Product focus differentiates Profit Leaders from Revenue Leaders**

#### 3. Overall Sales Efficiency Gap
- **Total Revenue:** ~$12.64M  
- **Total Profit:** ~$1.47M  
- **Overall Margin:** ~11.61%  

Margin dispersion ranges from **single-digit levels (US territories)** to **~26% (Canada)**.  

→ **Growth is consistent, but pricing effectiveness and execution quality vary significantly**

#### 4. Regional Impact on Profitability
- **US Regions (West, East, Central, South)** → **High revenue concentration, moderate margin**  
- **Canada (Nicole Hansen)** → **Smaller scale, highest efficiency**  
- **North Asia (Shirley Daniels)** → **Balanced growth, strong margin stability**  

→ **Less price-sensitive regions demonstrate stronger margin sustainability**

#### 5. Product-Level Profit Drivers by Agent
- **Phones (~$1.71M Revenue)** and **Copiers (~$259K Profit)** dominate contribution  
- Technology-focused agents outperform in **Margin Performance**  
- **Furniture-heavy portfolios** dilute profitability impact  

→ **Technology concentration = Structural advantage for top profit agents**

## 🔎 Final Conclusion & Recommendation  

| Strategy | Insight | Recommendation |
|-----------|----------|----------------|
| 🚀 **1. Market & Sales Expansion Strategy** | - The US acts as the primary **volume engine** (high revenue, ~11% margin). <br>- Canada delivers the **highest profitability (~26.6%)** despite small scale. <br>- North Asia maintains strong margin stability (~19.5%). <br>- EMEA & Africa show the fastest growth (~56–60% YoY). | - Maintain the US as the revenue base while improving pricing discipline. <br>- Selectively expand in Canada & North Asia to maximize margin. <br>- Increase investment in EMEA & Africa to capture high-growth momentum. |
| 🛒 **2. Product & Sales Portfolio Optimization** | - Technology is the **core profit driver (~14% margin)**. <br>- Phones & Copiers contribute the largest share of profit. <br>- Furniture drags overall margin (~7%). <br>- Sales agents focused on Technology achieve higher margins. | - Increase Technology mix within the sales portfolio. <br>- Upsell high-margin products (Phones, Copiers). <br>- Tighten control or rationalize low-margin Furniture lines. |
| 👥 **3. Sales Capability & Performance Gap** | - Revenue is partially concentrated among top performers (~$2.82M vs ~$0.9–1.6M). <br>- Significant margin gap across regions (11%–26%). | - Replicate best practices from high-margin agents across teams. <br>- Strengthen pricing and product-mix coaching in volume-driven regions. <br>- Shift KPIs from revenue-only to margin-based performance. |
| ⚙️ **4. Operational Efficiency & Risk Control** | - Orders grew >50% while return rate remained stable (~5%). <br>- Standard Class drives the majority of return volume due to scale. | - Sustain quality control during expansion. <br>- Optimize logistics costs rather than changing shipping structure. |
