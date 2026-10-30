# E-Commerce Acquisition, Cohort Retention & LTV Optimization Dashboard

[![Tableau Public](https://img.shields.io/badge/Tableau_Public-View_Interactive_Dashboard-E97627?style=for-the-badge&logo=tableau)](https://public.tableau.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

## Executive Summary
This end-to-end data analytics project evaluates customer acquisition efficiency, subscriber cohort retention, and customer lifetime value (LTV) for an e-commerce platform. Built using **Tableau Desktop** and a relational dataset (`customers.csv`, `orders.csv`, `subscriptions.csv`), this interactive dashboard bridges descriptive historical analytics with proactive financial scenario modeling.

![Dashboard Preview](assets/dashboard_preview.png)

---

## Key Business Questions Addressed
1. **Channel Performance:** Which acquisition channels generate the highest total top-line revenue versus average customer value?
2. **Cohort Health:** How do monthly subscriber cohorts retain over a 12–24 month lifecycle, and where does peak churn occur?
3. **Financial Sensitivity:** How do across-the-board promotional discount strategies impact channel-level net revenue?

---

## Technical Architecture & Tableau Implementation

### 1. Advanced Level of Detail (LOD) Expressions
To calculate individual customer lifetime value independent of view-level aggregations or active canvas filters, a `FIXED` Level of Detail expression was constructed at the `Customer_ID` grain:

```tableau
// Customer Total Revenue (LOD)
{ FIXED [Customer_ID] : SUM([Revenue]) }
