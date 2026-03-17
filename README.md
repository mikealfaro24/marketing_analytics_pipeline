# 📊 Marketing Analytics Pipeline (Databricks + Looker Studio)

## Project Background

This project simulates a real-world **marketing analytics workflow** for an e-commerce business. The goal was to design an end-to-end pipeline that transforms raw marketing data into actionable insights to support data-driven decision-making.

As a data analyst, this project focuses on understanding:

- Customer behavior  
- Marketing campaign performance  
- Traffic source effectiveness  
- Product engagement  

The pipeline follows a **modern data architecture approach**, using Databricks medallion layers to move from raw data to business-ready insights.

---

## 🔗 Project Links

- 📘 Full Documentation & Workflow (Notion):  
👉 https://mercury-capri-35c.notion.site/Marketing-Analytics-Pipeline-Performance-Dashboard-3458c9957353838691b401cf017b53aa?pvs=74

- 📊 Interactive Dashboard (Looker Studio):  
👉 https://lookerstudio.google.com/embed/reporting/1510c6bc-9e9b-4bf8-a47f-8947d2abfe3b/page/VyIqF

---

## Data Structure & Architecture

The project uses a **star schema analytical model** built on top of a Databricks medallion architecture:

**Source Systems (Excel) → Data Prep → Bronze → Silver → Gold → Dashboard**

### Tables

- `fact_marketing_performance` → Core fact table (sessions, purchases, revenue)  
- `dim_campaign` → Campaign details and budget  
- `dim_channel` → Traffic source (UTM parameters)  
- `dim_device` → Device type  
- `dim_category` → Product category  
- `dim_customer` → Customer demographics  

---

### Entity Relationship Diagram

![ERD](https://github.com/mikealfaro24/marketing_analytics_pipeline/blob/11a5fe627c868e96b73087e6a35ebafec5233567/docs/shoply_ERD.png)

---

## Executive Summary

### Overview of Findings

This analysis reveals that **search and social channels drive the majority of revenue**, while **email and promotional campaigns generate the highest conversion efficiency**. Additionally, **mobile dominates traffic**, but **desktop users convert at higher rates**, and **customers aged 25–44 represent the core revenue segment**.

Key takeaways:

- High-ROI campaigns (flash sales, bundles) outperform others  
- Mobile drives traffic, desktop drives conversions  
- Core customers (25–44) generate most revenue  

---

### Dashboard Snapshot

![Dashboard](https://github.com/mikealfaro24/marketing_analytics_pipeline/blob/f88fdb7b11be68157daeac356a8ae46278bfd456/dashboard/dashboard_preview.png)

---

## Insights Deep Dive

### 1. Traffic Source Performance

- Google drives the highest total revenue due to scale  
- Facebook delivers the highest revenue per session  
- Email has the strongest conversion rates  
- Referral traffic shows lower efficiency  

---

### 2. Campaign ROI & Budget Efficiency

- Flash sale campaigns generate the highest ROI (up to 4x return)  
- Bundle and seasonal campaigns perform consistently well  
- High budget does not guarantee strong returns  
- New arrival campaigns are less efficient and more awareness-focused  

---

### 3. Device & User Behavior

- Mobile drives the majority of sessions and revenue  
- Desktop users have the highest conversion rates  
- Tablet usage is minimal but still effective  
- Users likely browse on mobile and convert on desktop  

---

### 4. Customer Segmentation

- Customers aged 25–44 (U.S.) generate the most revenue  
- Ages 45–54 show strong revenue per customer  
- Younger users (18–24) show strong engagement  
- Missing demographic data highlights data quality gaps  

---

## Recommendations

Based on the analysis, the following actions are recommended:

- Reallocate budget toward high-performing campaigns (flash sales, bundles)  
- Optimize underperforming campaigns through better targeting and messaging  
- Improve mobile UX while refining desktop checkout experience  
- Focus marketing efforts on high-value customer segments (25–44)  
- Improve data quality in customer demographics and product categorization  

---

## Assumptions & Caveats

- Dataset is **synthetic**, so conversion rates may be higher than real-world benchmarks  
- Some demographic data is missing and labeled as unknown  
- Campaign attribution is simplified (no multi-touch attribution)  
- Product categories labeled as “unknown” indicate missing classification  
- Most data cleaning was performed in Excel due to the learning curve of simultaneously working with Databricks, the medallion architecture, and PySpark. This allowed for faster prototyping and validation of the data model. In a production environment, these transformations would be implemented within the Silver layer using PySpark to ensure scalability, reproducibility, and better pipeline management. This project can be further improved by fully refactoring the cleaning and transformation steps directly within Databricks.
---

## ⚙️ Tech Stack

- Databricks (SQL / PySpark / Data Engineering)  
- Medallion Architecture (Bronze, Silver, Gold)  
- Looker Studio (Dashboarding)  
- Excel (Source Data)  

---
