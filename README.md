# StreamPlus Subscription Analysis

An end-to-end **Power BI** dashboard that analyses subscription revenue, payments, customers and customer support for **StreamPlus**, a streaming subscription service.

The report has 14 pages covering revenue trends, payment health, customer acquisition and geography, and support-ticket satisfaction.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Business Questions Answered](#business-questions-answered)
- [Data Model](#data-model)
- [Key DAX Measures](#key-dax-measures)
- [Dashboard Pages](#dashboard-pages)
- [Tools & Techniques](#tools--techniques)
- [Repository Structure](#repository-structure)
- [How to Open the Project](#how-to-open-the-project)
- [Author](#author)

---

## Project Overview

StreamPlus needs to understand how its subscription business is performing. This project turns the payments, customer and support-ticket data into an interactive Power BI report that helps stakeholders:

- Track **revenue** by month, quarter and year
- Monitor **payment success** and the mix of payment methods
- Understand **where customers come from** (acquisition channel and region)
- Identify **high-value (premium) customers**
- Measure **customer satisfaction (CSAT)** and support performance

---

## Business Questions Answered

1. How is total revenue trending monthly, quarterly and yearly?
2. What is the month-over-month revenue growth rate?
3. What share of payments are successful, and how do payment statuses and methods break down?
4. Which streaming quality tiers (plans) are most popular?
5. Which acquisition channels and regions bring in the most customers?
6. Who are the highest-paying (premium) customers?
7. What is the average CSAT score, and which ticket categories drive the most tickets?
8. Is there a relationship between ticket resolution time and customer ratings?
9. Is there seasonality in support-ticket volume?
10. Which tickets need urgent monitoring?

---

## Data Model

The model uses a star-schema style design:

| Table | Type | Description |
|-------|------|-------------|
| `Fact_Payments` | Fact | Payment transactions (status, payment method, plan, customer) |
| `Fact_Tickets` | Fact | Customer support tickets (category, resolution time, CSAT score) |
| `Dim_Customers` | Dimension | Customer details (name, city, region, acquisition channel) |
| `Calender` | Dimension | Date table (Month-Year, Quarter-Year, Year) |
| `_Measures` | Measures table | Holds all DAX measures used in the report |

---

## Key DAX Measures

All measures live in the `_Measures` table:

- `Total Payment Amount`
- `Total_Successful_Payment_Amount`
- `Total_Successful_Payments`
- `% of Successful_payment`
- `Previous_month_total_revenue`
- `Month_over_month_growth_rate`
- `Payment Status Count`
- `Payment_Method_Count`
- `Total_Customers`
- `Total Tickets`
- `Avg_CSAT_Score`
- `Urgent_Monitoring_Live`

---

## Dashboard Pages

| # | Page | Visuals Used | What It Shows |
|---|------|--------------|---------------|
| 1 | **Profile** | Text box | Author details |
| 2 | **Payment Status and Method Count** | Donut, pie, KPI cards | Split of payments by status and by payment method, plus total payment amount |
| 3 | **CSAT Score** | KPI card | Average customer satisfaction score |
| 4 | **Revenue Page** | 3 line charts | Revenue by month, quarter and year |
| 5 | **Acquisition Channel** | 2 donut charts | Customers by acquisition channel and by region |
| 6 | **Regional Customer Distribution** | Matrix | Customers by region, city and acquisition channel |
| 7 | **Premium Customers** | Table | Customers ranked by total payment amount |
| 8 | **Customer Satisfaction** | Treemap, KPI card | Ticket volume by category and average CSAT |
| 9 | **Resolve Days vs Ratings** | Scatter chart | Resolution time against CSAT score |
| 10 | **Urgent Monitoring** | KPI card | Live count of tickets flagged as urgent |
| 11 | **Payment Success Rate Tracking** | Gauge, KPI card | Successful payment rate and total successful payments |
| 12 | **Popularity of Streaming Quality Tiers** | Clustered column chart | Customer count by subscription plan |
| 13 | **Month-over-Month Growth** | Waterfall, table, KPI card | Monthly revenue, previous month revenue and growth rate |
| 14 | **Ticket Seasonality** | Area chart | Ticket volume over time |

---

## Tools & Techniques

- **Power BI Desktop** for report design and visuals
- **Data modelling** with a star schema, relationships and a dedicated date table
- **DAX** for measures such as month-over-month growth, success rate and CSAT
- **Visualization types:** KPI cards, donut/pie, line, area, waterfall, scatter, treemap, gauge, matrix and table

---

## Repository Structure

```
streamplus_subscription_analysis/
│
├── streamplus_subscription_analysis.pbix   # Power BI report file
├── README.md                               # Project documentation
└── screenshots/                            # (optional) dashboard images
```

---

## How to Open the Project

1. Download or clone this repository:
   ```
   git clone https://github.com/<your-username>/streamplus_subscription_analysis.git
   ```
2. Install the free [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows).
3. Open `streamplus_subscription_analysis.pbix` in Power BI Desktop.
4. Use the page tabs at the bottom to move through the dashboard.

> **Note:** `.pbix` files open only in Power BI Desktop or the Power BI Service. GitHub cannot preview them.

---

## Author

**Pakshal D Shah**
Email: 31shahshah31@gmail.com

---



