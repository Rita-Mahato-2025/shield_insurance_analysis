![Logo](images/Shield_Insurance.png)
# Insurance Policy Sales & Settlement Analysis
### 🧩 Domain: Insurance
End-to-End Power BI Project | Dimensional Modeling | Customer Demographics | Age Group Insights

**Live Dashboard:** [Click here](https://app.powerbi.com/view?r=eyJrIjoiM2M2NWE2NzctMjBmMi00ZWIxLWIyNTItNGFlNWMxOTljMWMwIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)

---

## 📌 Table of Contents
- <a href="#overview">Project Overview</a>
- <a href="#dataset-description">Dataset Description</a>
- <a href="#dimensional-model">Dimensional Model</a>
- <a href="#business-questions">Business Questions</a>
- <a href="#features-built">Features Built</a>
- <a href="#dax-measures">DAX Measures</a>
- <a href="#tools-used">Tools Used</a>
- <a href="#conclusion">Conclusion</a>
- <a href="#author--contact">Author & Contact</a>

---

## 🧾 Project Overview

This project analyzes customer behavior, policy performance, and settlement trends for an insurance company using dimensional modeling and Power BI.
The goal is to help stakeholders understand:

•	Revenue trends

•	Customer growth

•	Sales mode performance

•	Age-group behavior

•	City-level segmentation

•	Settlement patterns

The project follows a clean Ask → Prepare → Process → Analyze → Share lifecycle.

## 🧩 Dataset Description

### The project is based on 5 CSV files:

•	dim_customer.csv – Customer details

•	dim_date.csv – Calendar table

•	dim_policies.csv – Policy information

•	fact_premiums.csv – Policy purchase transactions

•	fact_settlements.csv – Age-wise settlement percentages

### Dimensional model:

•	dim_customer → fact_premiums (1:many)

•	dim_date → fact_premiums (1:many)

•	dim_policies → fact_premiums (1:many)

•	dim_age (created in Power Query) → dim_customer (1:many)

## 🎯 Business Questions

### Sales Performance

•	What is the total revenue and monthly revenue trend?

•	Which sales mode performs best (Agent, Direct, App, Website)?

•	What is the daily & monthly customer growth rate?

### Customer Demographics

•	Which cities contribute the most revenue?

•	How do revenue and customer counts vary by city and age group?

### Age Group Analysis

•	Which age group buys more policies?

•	Which age group prefers which sales mode?

•	What is the expected settlement by age segment?

## 💡 Features Built (KPIs & Visuals)

## Key Metrics:

•	Total Customers

•	Total Revenue

•	Daily Revenue Growth Rate

•	Daily Customer Growth Rate

•	Monthly Revenue & Customer Trend

•	Revenue Split by Sales Mode

•	Customer Segmentation by City & Age Group

## Filters:

•	Sales Mode

•	Age Group

•	City

•	Month

•	Policy ID

## 🖥 Report Pages

### 1️⃣ Sales Mode Analysis

•	Customer by sales mode

•	Monthly trend (line chart)

•	Revenue split (pie chart)

•	Revenue by sales mode

### 2️⃣ Customer Demographics

•	Customer distribution by city

•	Revenue distribution

•	Age group segmentation

•	Growth insights

### 3️⃣ Age Group Analysis

•	Customers by age group

•	Revenue by age group

•	Policy preference per age segment

•	Sales mode preference per age segment

•	Expected settlement % (standalone insight)

## 🧮 Important DAX Measures

Total Customers =
DISTINCTCOUNT(fact_premiums[customer_code])

Total Revenue =
SUM(fact_premiums[final_premium_amt(INR)])

Daily Revenue Growth = 
VAR PrevDay = CALCULATE([Total Revenue], DATEADD(dim_date[date], -1, DAY))
RETURN DIVIDE([Total Revenue] - PrevDay, PrevDay)

Daily Customer Growth = 
VAR PrevDay =
    CALCULATE(
        [Customers Per Day],
        DATEADD(dim_date[date], -1, DAY)
    )
RETURN
DIVIDE([Customers Per Day] - PrevDay, PrevDay)

## 🛠 Tools Used

•	Power BI

•	Power Query (ETL)

•	MySQL (optional)

•	Excel (data cleaning)

## 📌 Conclusion

This report provides a 360° view of the insurance business, enabling stakeholders to:

•	Understand revenue & customer behavior

•	Identify high-value age groups & cities

•	Optimize sales channels

•	Forecast settlement risk

<h2><a class="anchor" id="author--contact"></a>Author & Contact</h2>

**Rita Mahato**  

Data Analyst 

📧 Email: ds.rita.mahato@gmail.com  

🔗 [LinkedIn](https://www.linkedin.com/in/mahato-rita/)  


