# SQL Analytics Practice

## Overview

This project demonstrates common SQL patterns. The analysis is performed using DuckDB in a Google Colab notebook and is based on a synthetic user-event dataset that simulates user behavior in an e-commerce application.

The goal of this project is to practice writing production-style analytical SQL queries, applying window functions, working with Common Table Expressions (CTEs), performing cohort and funnel analysis, and reasoning about query performance at scale.

---

## Dataset

The dataset is generated programmatically and contains:

* **10,000 users**
* **~200,000 events**
* User attributes:

  * `user_id`
  * `signup_date`
  * `country`
  * `marketing_channel`
* Event attributes:

  * `event_id`
  * `user_id`
  * `event_time`
  * `event_type`

## Simulated User Funnel

```
signup
  ↓
view_product
  ↓
search
  ↓
add_to_cart
  ↓
purchase
```

Users do not necessarily complete every step, creating realistic drop-off behavior for funnel analysis.

---

## SQL Exercises

### 1. Retention Cohort Analysis

**Objective:** Measure user retention by signup cohort.

Concepts demonstrated:

* Cohort analysis
* CTEs
* Window functions
* Retention calculations
* Aggregations

Key metric:

```
Retention Rate =
Active Users in Week N / Users in Week 0
```

---

### 2. Funnel Analysis

**Objective:** Measure how users progress through a multi-step product funnel.

Funnel analyzed:

```
view_product
    ↓
search
    ↓
add_to_cart
```

Concepts demonstrated:

* Conditional aggregation
* Event sequence analysis
* Timestamp comparisons
* Conversion funnel measurement

---

### 3. First Event Per User

**Objective:** Identify the first event associated with each user.

Concepts demonstrated:

* `ROW_NUMBER()`
* Window functions
* Deduplication
* Partitioning

---

### 4. Rolling 7-Day Average

**Objective:** Calculate a rolling average of daily purchases.

Concepts demonstrated:

* Window functions
* Moving averages
* Time-series analysis
* Trend smoothing

Example metric:

```
Daily Purchases
7-Day Rolling Average
```

---

### 5. Query Performance Analysis

**Objective:** Analyze a query that would become inefficient on a large table.

Concepts demonstrated:

* Query optimization
* Execution plans
* Indexing considerations
* Sequential scans
* Performance reasoning

Topics discussed:

* `EXPLAIN`
* `EXPLAIN ANALYZE`
* Sargable predicates
* Index utilization
* Large-scale query performance

---

## Technologies

* SQL
* DuckDB
* Python
* Pandas
* Google Colab

---

## Key SQL Concepts Covered

* Common Table Expressions (CTEs)
* Window Functions

  * `ROW_NUMBER()`
  * `AVG() OVER()`
  * `MAX() OVER()`
* Aggregations
* Cohort Analysis
* Funnel Analysis
* Deduplication
* Time-Series Analytics
* Query Optimization
* Execution Plan Analysis

---

These exercises reflect common tasks encountered in product analytics, business intelligence, data science, and data engineering workflows.
