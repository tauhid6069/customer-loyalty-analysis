# 🛒 Customer Loyalty Analysis – Supermarket (Power BI Dashboard)

## 📌 Project Overview
This project explores **customer loyalty and retention** using the popular **Online Retail Dataset (UCI / Kaggle)**.  
The goal is to **analyse purchase behavior**, segment customers, and build **interactive dashboards** to track loyalty metrics such as repeat rate, cohort retention, and segment contribution.

The analysis is delivered as a **Power BI report** with drill-through capabilities for both **Customer-level** and **Product-level** insights.

---

## 🎯 Objectives
- Measure **new vs repeat customer revenue**
- Calculate **churn / lost customers** and **retention rates**
- Perform **Cohort Analysis** (first purchase month vs subsequent months)
- Segment customers using **RFM (Recency, Frequency, Monetary) Analysis**
- Identify **Champions, Loyal, At Risk, and Lost** customer groups
- Enable **drill-through pages** for customer journeys and product performance

---

## 📂 Dataset
- **Source:** [UCI Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/online+retail) / Kaggle mirrors available  
- **Period Covered:** Dec 2010 – Dec 2011  
- **Transactions:** ~500k rows  
- **Fields:**
  - `InvoiceNo` – Transaction number
  - `StockCode` – Product identifier
  - `Description` – Product name
  - `Quantity` – Units purchased
  - `InvoiceDate` – Date of purchase
  - `UnitPrice` – Price per unit
  - `CustomerID` – Unique customer identifier
  - `Country` – Customer location

---

## 🔑 Key Metrics
- **Customers:** Total unique customers
- **Repeat Customers:** Customers who made more than one purchase
- **Orders:** Distinct invoices
- **Revenue:** Total sales amount
- **AOV (Average Order Value):** Revenue ÷ Orders
- **Repeat Revenue %:** Share of sales from repeat buyers
- **Lost Customers:** Customers active in the previous month but not returning
- **Retention Rate (Cohort):** Share of cohort customers purchasing again

---

## 📊 Dashboard Pages

### 1. **Executive Dashboard**
- **KPIs:** Customers, Repeat Customers, Revenue, Orders, AOV
- **Cohort Retention Matrix** – Heatmap of customer retention
- **New vs Repeat Revenue** – Stacked column chart by month
- **Segment Contribution** – Revenue by RFM segments (customer type)
- **Lost Customers by Month** – Distribution of monthly lost customers

### 2. **Customer Detail (Drill-through)**
- **KPIs:** Repeat Rate, Repeat Revenue %, Revenue, Orders, Avg Repeat, AOV
- **Donut:** New vs Repeat revenue for selected customer
- **Column:** Revenue trend by month
- **Transaction table:** Purchase date, Customer ID, Invoice, Product, Segment, IsRepeat (Check if the customer is a returning customer)

### 3. **Product Detail (Drill-through)**
- **KPIs:** Product Revenue, Repeat Revenue %, Distinct Customers, AOV
- **Bar:** New vs Repeat revenue by item
- **Donut:** Count of items by segment
- **Table:** Customers who purchased the product

---

## 🧮 Methods & Theory

### **1. RFM Segmentation**
- **Recency:** Days since last purchase  
- **Frequency:** Number of orders  
- **Monetary:** Total spend  
- Segments are derived from RFM scores → Champions, Loyal, At Risk, Lost, etc.

### **2. Cohort Analysis**
- Groups customers by **first purchase month**
- Tracks retention across subsequent months
- Shows stickiness of newly acquired customers

### **3. Churn & Retention**
- **Lost Customers % = (Prev Month Customers – Retained) ÷ Prev Month Customers**  
- **Retention % = Retained ÷ Prev Month Customers**

### **4. New vs Repeat Revenue**
- Split using `IsRepeat` flag:
  ```DAX
  IsRepeat =
  IF ( OnlineRetail[InvoiceDate] > OnlineRetail[FirstPurchaseDate], 1, 0 )
  ```
  - Allows revenue breakdown by first-time vs returning buyers.
  
---

## ⚙️ Tech Stack

Power BI Desktop – Data modelling & visualization

DAX – Measures for KPIs, Cohorts, Segments

Power Query – ETL (cleaning, filtering returns, handling null IDs)

GitHub – Project versioning & documentation

---

## 📸 Sample Dashboard Screens
- Main Dashboard

![Executive Dash](https://github.com/user-attachments/assets/f9109f95-cc64-44b1-904e-b827f3dadf7f)

- Customer Detail Drill-through

![Customer details](https://github.com/user-attachments/assets/b30c4245-9c61-4c48-b6d3-5dbae084961f)

- Product Detail Drill-through

![Product dash](https://github.com/user-attachments/assets/a98b3636-fa32-4b20-8570-7739fa82f3ac)


---

## 🚀 How to Use

Download the .pbix file from this repo.

Open in Power BI Desktop (latest version).

Load the Online Retail dataset (CSV/Excel) from UCI/Kaggle.

Refresh the report → all visuals & measures update automatically.

Explore:

Use slicers (Date, Country)

Drill-through from products/customers

Reset filters with the Reset button

---

## 📈 Business Impact

- Identifies loyalty drivers and high-value customers

- Helps optimise promotions and CRM campaigns

- Detects customer churn early

- Prioritises products with strong repeat purchase behavior

---

## 👤 Author

Md Tauhidul Islam

🔗 [[LinkedIn Profile](https://www.linkedin.com/in/tauhidul-islam/)]
