# Maven Market Sales & Returns Report

A Power BI Desktop project that turns Maven Market's raw sales, returns, and store data into a governed data model and an interactive "Topline Performance" dashboard — built to answer which brands drive volume without eating into margin or driving returns, and how sales trend by month and region.

## Overview

Maven Market leadership needed a fast, reliable way to track brand performance, monthly trends, and regional sales without waiting on manual spreadsheet pulls. This project delivers a complete BI workflow: raw multi-source CSV data → a governed star/snowflake data model → a reusable DAX measure library → a decision-oriented dashboard.

**Key results surfaced by the dashboard:**
- 💰 **$1,199,308** total revenue | **59.68%** profit margin | **566,716** units sold | **1.00%** return rate

## What's Inside

- **`MavenMarket_Report.pbix`** — the finished Power BI report
- **7 connected data tables**, including a combined 1997–1998 `Transaction_Data` table built from a folder of yearly CSVs
- **21 DAX measures** in a dedicated Measure Table, covering core aggregations, weekend/percent-of-total analysis, and time intelligence (YTD, 60-day rolling, month-over-month)
- **8 calculated columns** added across the lookup tables

## Data Model

Built as a star schema for `Transaction_Data` and `Return_Data`, with a snowflake extension from `Stores` to `Regions`. All relationships are one-to-many, filtering flows one-way from lookup tables downstream, and only one date relationship per data table is active at a time — keeping the model clean and predictable.

## Dashboard: "Topline Performance"

- **Brand matrix** — top 30 brands by transaction volume, with Profit Margin and Return Rate color scales to spot margin/quality risks at a glance
- **KPI trend cards** — current month vs. last month for transactions, profit, and returns
- **Map & treemap** — regional sales by country, state, and city
- **Weekly revenue trend** — 1998 revenue by week
- **Revenue vs. target gauge** — actuals against a rolling 5% month-over-month lift target

## Business Insights

A few examples of what the model surfaces:
- **USA leads regional volume** (93,986 transactions), but **Mexico is close behind at 40%** of total volume, not a distant third
- **Washington state alone accounts for ~49%** of all USA transactions — a clear signal for where to weight marketing and logistics spend
- **Weekend transactions make up 27.6%** of total volume, informing staffing and promotion timing
- Brand-level margin vs. return-rate comparisons (e.g., Horatio vs. Cormorant) flag quality or pricing issues before they erode profit further

## Tools

Power BI Desktop · Power Query · DAX

*Built as part of the "Microsoft Power BI Desktop for Business Intelligence" course, Maven Analytics.*
