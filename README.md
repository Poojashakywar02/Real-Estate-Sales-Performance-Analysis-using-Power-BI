# Real-Estate-Sales-Performance-Analysis-using-Power-BI
Business Problem

A real estate organization needed better visibility into its sales performance, property utilization, and agent productivity. The business lacked a centralized reporting system to:

Track actual sales vs targets
Monitor property status (vacant, occupied, unlisted)
Identify top-performing agents and projects
Understand regional (state-wise) sales trends
Analyze customer payment behavior and deal stages

The goal of this project was to build an interactive Power BI dashboard that enables stakeholders to make data-driven decisions to improve revenue, optimize property management, and enhance sales strategy.

Dataset Overview

The dataset includes multiple interconnected tables capturing:

Property Details – Property ID, description, project association
Agent Information – Agent names and sales contribution
Sales Transactions – Revenue, order value, payment method
Project Data – Project-wise revenue and performance
Geographical Data – State-wise sales distribution
Status Data – Property stage (Open, Completed, In-Process), occupancy status
Approach & Methodology
1. Data Preparation (Power Query)
Imported and combined multiple datasets
Cleaned and transformed data by:
Handling null/missing values
Removing duplicates
Standardizing formats (currency, dates)
Created derived columns for better analysis (e.g., status grouping)
2. Data Modeling
Built a relational data model with fact and dimension tables
Established relationships:
Properties ↔ Agents
Sales ↔ Projects
Transactions ↔ Payment Types
Optimized model for performance using star schema design
3. Key Metrics & DAX Calculations

Total Sales

Total Sales = SUM(Sales[Amount])

Target Sales

Target = SUM(Target[Target Amount])

Revenue

Revenue = SUM(Sales[Revenue])

Property Count

Total Properties = COUNT(Properties[Property ID])

Occupancy Distribution

Occupied = CALCULATE(COUNT(Properties[Property ID]), Properties[Status] = "Occupied")
Vacant = CALCULATE(COUNT(Properties[Property ID]), Properties[Status] = "Vacant")
Unlisted = CALCULATE(COUNT(Properties[Property ID]), Properties[Status] = "Unlisted")

Sales vs Target Variance

Variance = [Total Sales] - [Target]
4. Dashboard Development

Developed a two-page interactive dashboard with the following features:

Page 1: Sales Overview
KPI Cards:
Total Sales ($2.08M)
Target ($1.84M)
Revenue ($2.68M)
Total Properties (275)
Property Status Summary:
Vacant (53), Occupied (47), Unlisted (35)
Agent Contribution (Bar Chart)
Monthly Trends:
New vs Sold Properties (Line Chart)
Actual vs Target (Bar + Line Combo)
Revenue by Project (Donut Chart)
Year-based slicer for dynamic filtering
Page 2: Operational Insights
Stage-wise Distribution (Open, Completed, In-Process)
Payment Mode Analysis:
Online Transfer, Cash, Cheque, Draft
State-wise Sales (Map Visualization)
Detailed Property Table:
Property ID, Agent, Description
Revenue Distribution (Decomposition Tree):
Drill-down by Project → Agent → Property Status
Interactive filters for:
Project Name
Agent
Property Status
Key Insights & Findings
Total Sales exceeded target, indicating strong business performance
Top Performing Agent: Richard contributed the highest revenue (~$928K)
Best Performing Project: Project-5 generated the highest revenue (~$1.12M)
Property Insights:
Majority properties are occupied, but a notable portion remains vacant (optimization opportunity)
Sales Trends:
Sales peaked mid-year and showed fluctuations across months
Payment Trends:
Online transfers (47%) are the most preferred payment method
Stage Analysis:
40% properties are still in “Open” stage → potential pipeline for future revenue
Geographical Insight:
Certain states contribute significantly more to revenue, indicating high-demand regions
Business Recommendations
Improve Inventory Utilization:
Focus on reducing vacant and unlisted properties through targeted marketing
Agent Performance Strategy:
Replicate strategies used by top-performing agents (e.g., Richard) across the team
Project Investment Decisions:
Invest more in high-performing projects like Project-5
Regional Expansion:
Increase marketing spend in high-performing states and explore low-performing regions
Digital Payment Optimization:
Enhance online payment systems since it is the most preferred method
Pipeline Acceleration:
Convert “Open” stage properties faster through promotions or pricing strategies
Tools & Technologies Used
Power BI – Dashboarding & Visualization
Power Query – Data Cleaning & Transformation
DAX (Data Analysis Expressions) – KPI & Metrics Creation
Excel/CSV – Data Source
Impact

This dashboard enabled stakeholders to:

Monitor real-time sales performance vs targets
Identify revenue-driving agents and projects
Optimize property utilization and inventory
Gain insights into customer behavior and regional trends
Make data-driven strategic decisions
