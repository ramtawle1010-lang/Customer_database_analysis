Exploring Customer Behavior Through Database Analysis (SQL Case Study)

GitHub Repository Description: A end-to-end SQL case study using MS SQL Server to analyze online food delivery transactions, customer cohort behavior, and premium loyalty program performance.n

📌 Project Overview

This repository contains a comprehensive data analytics case study focused on uncovering customer behavior patterns, consumption trends, and loyalty engagement for an online food delivery platform.

By querying a relational database containing transaction history, product catalogs, and loyalty membership signups, we answer critical business questions to help drive strategic decisions on customer retention, menu engineering, and loyalty program expansion.

🗃️ Database Schema

The analysis leverages 5 interconnected relational tables:

project_user_name: Customer metadata (User IDs matched with names).

project_users: User registration records and onboarding dates.

project_product: Menu catalog mapping unique item IDs, names, and retail prices.

project_sales: Transactional logs tracking purchase dates and items bought by users.

project_goldusers_signup: Onboarding timestamps for users who upgraded to the premium "Gold" loyalty tier.

                  ┌──────────────────────┐
                  │  project_user_name   │
                  └──────────┬───────────┘
                             │ (userid)
                             ▼
  ┌──────────────┐     ┌──────────────┐     ┌─────────────────────────┐
  │project_users ├────►│project_sales │◄────┤project_goldusers_signup │
  └──────────────┘     └──────┬───────┘     └─────────────────────────┘
            (userid)          │             (userid)
                              ▼ (product_id)
                       ┌──────────────┐
                       │project_product│
                       └──────────────┘


🚀 Key Business Questions Solved

The SQL scripts in this repository solve 20 strategic business queries organized into distinct analytical dimensions:

1. Financial & Revenue Performance

Total sales revenue generated per menu item.

Identification of the top 3 highest-revenue-generating products.

Year-over-Year (YoY) growth trends and annual revenue fluctuations.

2. Loyalty Program Analysis (Standard vs. Gold Members)

Membership acquisition and standard-to-premium conversion rates.

Total and individual customer revenue generated during active Gold status.

Ordering behavior shift (order frequency and spend) before vs. after joining the Gold tier.

3. Customer Engagement & Behavior Metrics

Lifetime Value (LTV) and individual transaction tallies per user.

On-platform engagement frequency (active visit days).

First-purchase behavior (establishing user initial tastes).

Item preferences and favorite dish classifications per customer.

🛠️ Tech Stack & SQL Competencies

Database Engine: MS SQL Server (T-SQL)

IDE: SQL Server Management Studio (SSMS)

Advanced SQL Concepts Applied:

Window Functions: DENSE_RANK(), ROW_NUMBER(), LAG() for trend and sequence analysis.

Common Table Expressions (CTEs): Used to isolate multi-step aggregations cleanly.

Conditional Logic & Type Casting: Applying CASE WHEN statements with strict CAST/CONVERT transformations for clean data reports.

Multi-Table Relational Joins: Connecting normalized schemas using optimized INNER JOIN and LEFT JOIN keys.

📂 Repository Structure

schema_creation.sql: DDL commands to set up database constraints and tables.

data_insertion.sql: Populates the database tables with transactional mock records.

case_study_queries.sql: Documented SQL solutions for all 20 business problems.

customer_behavior_sql_case_study.html: Interactive, visually responsive slide presentation summarizing key findings.
