# Customer Value & Revenue Analysis: RFM Segmentation and CLV-Driven Pricing Strategy

## Table of Contents
- [Project Background](#project-background)
- [Business Objective](#business-objective)
- [Data Overview](#data-overview)
- [Analytical Approach](#analytical-approach)
- [Executive Summary of Results](#executive-summary-of-results)
    - [Key Findings](#key-findings)
    - [Business Impact](#business-impact)
- [Detailed Analysis & Insights](#detailed-analysis--insights)
    - [Revenue Concentration Analysis](#revenue-concentration-analysis)
    - [Customer Segmentation (RFM Analysis)](#customer-segmentation-(rfm-analysis))
    - [Customer Lifetime Value Estimation](#customer-lifetime-value-estimation)
    - [Pricing Strategy Framework](#pricing-strategy-framework)
- [Strategic Recommendations](#strategic-recommendations)
- [Implementation Roadmap](#implementation-roadmap)
- [Assumptions & Limitations](#assumptions--limitations)
- [Future Work](#future-work)
- [Technologies Used](#technologies-used)

## Project Background
In e-commerce and online retail, sustainable growth depends not only on sales volume but on understanding which customers drive the most value, how their behavior evolves over time, and which strategies maximize long-term revenue while maintaining healthy unit economics.

This project analyzes **1.06M+ transactions** from a UK-based online gift retailer (2009-2011) to build an end-to-end customer analytics framework that identifies **£1.45M in revenue preservation and growth opportunities** through segment-specific pricing and retention strategies. The analysis demonstrates how to shift resource allocation from volume-driven to value-weighted approaches using data-driven customer segmentation and lifetime value modeling.

All code, methodology, and detailed analysis can be found in the Jupyter notebook: [GitHub Repository Link](https://github.com/ChisomChioke/Customer-Value-Revenue-Optimization-in-Online-Retail/blob/main/Customer_Value_%26_Revenue_Optimization.ipynb). A one-page summary is contained in this document: [1-page Summary](https://drive.google.com/file/d/1wCHCl68QhohyY__U6K_cSh8gBmKT_qJF/view)

## Business Objective
Most customer engagement strategies apply uniform pricing, discounts, and retention spending across the entire customer base, ignoring that customer value is highly concentrated and unevenly exposed to churn risk. This misallocates resources by over-investing in low-value segments while under-protecting high-value customers, ultimately eroding both margin and long-term profitability.

**This project addresses three critical business questions:**

1. **Value Identification:** Which customers generate disproportionate value, and how is that value created (frequency vs. spend)?

2. **Churn Risk Assessment:** Which high-value customers face the greatest attrition risk, and what is the revenue exposure?

3. **Resource Allocation:** How should pricing, discounts, and retention investments be differentiated by customer segment to maximize ROI?

The analysis constructs a framework linking **segmentation → lifetime value → pricing strategy**, enabling efficient allocation of retention spend and pricing flexibility aligned with customer behavior rather than arbitrary rules.

## Data Overview

**Dataset:** [Online Retail II dataset](https://archive.ics.uci.edu/dataset/502/online+retail+ii) from UCI Machine Learning Repository

**Coverage:** 1,067,371 transaction records | December 2009 - December 2011 | 41 countries

**After cleaning:** 805,549 valid transactions from 5,942 unique customers

**Data Preparation:**

- Removed 23% of transactions missing Customer IDs (non-registered purchases)
- Filtered cancellations and returns (negative quantities/prices)
- Aggregated line-items to customer-transaction level
- Created RFM metrics for segmentation

## Analytical Approach

The analysis follows a structured four-phase methodology:

**Phase 1: Exploratory Analysis**

- Revenue distribution and concentration patterns (Pareto analysis)
- Customer-level metrics: total revenue, order frequency, average order value
- Temporal patterns and purchasing behavior

**Phase 2: RFM Segmentation**

- **Recency:** Days since last purchase (proxy for churn risk)
- **Frequency:** Total number of orders (engagement level)
- **Monetary:** Total revenue generated (historical value)
- Created 6 behavioral segments: Champions, Potential Loyalists, Loyal Customers, At-Risk (High Value), New Customers, Hibernating

**Phase 3: Customer Lifetime Value (CLV) Estimation**

- Constructed behavioral CLV proxy using frequency, AOV, and recency-adjusted retention
- Segment-level CLV aggregation to identify value concentration
- Churn exposure assessment (90-day inactivity threshold)

**Phase 4: Pricing Strategy Design**

- Segment-specific pricing recommendations aligned with CLV and churn risk
- ROI framework comparing retention vs. acquisition efficiency
- Quantified revenue opportunities by strategic intervention

## Executive Summary of Results

### Key Findings

**1. Extreme Revenue Concentration**

- **15% of customers (Champions) generate 62% of revenue (£10.9M)**
- Top 20% of customers drive 77% of total revenue
- Bottom 50% contribute only 6% of revenue

![Pareto Analysis](images/pareto_analysis.png)
_Figure 1: Pareto analysis reveals that 23% of customers generate 80% of revenue, validating the need for targeted, value-weighted retention strategies._

**2. Revenue Share vs. Customer Count Imbalance**

Champions represent just 15% of the customer base but drive 62% of total revenue, while Hibernating customers account for 35% of customers but contribute only 7% of revenue—a 5:1 customer-to-value mismatch that would be invisible with uniform engagement strategies.

![Customer Proportion vs. Revenue Contribution](images/customer_proportion_vs_revenue_contribution.png)
_Figure 2: Customer proportion vs. revenue contribution reveals extreme imbalance. Treating all customers equally would massively misallocate resources._

**3. Customer Lifetime Value Varies 20x Across Segments**

Champions demonstrate 20x higher CLV (£12,494) than Hibernating customers (£611) through:

- **Frequency advantage:** 22 orders vs. 1.7 orders (13x difference)
- **Spending power:** £459 average order value
- **Strong recency:** 18 days vs. 440 days inactive

Similar total revenue can arise from fundamentally different behaviors—high frequency with moderate AOV vs. infrequent high-value purchases—requiring differentiated pricing strategies.

**4. CLV-Risk Asymmetry: At-Risk Segment Represents Concentrated Revenue Exposure**

- **At-Risk (High Value):** 5% of customers, £1.0M revenue (6%), **100% churn exposure** (338 days avg inactivity)
- Losing this segment would cost **3.8x more** than the revenue generated by acquiring equivalent new customers
- Reactivating just one **At-Risk customer (£3,854 avg value)** preserves the same revenue as acquiring **3.8 new customers (£1,010 each)**

![Segment Strategy Framework](images/segment_strategy_framework.png)
_Figure 3: Segment strategy framework showing customer count, revenue contribution, CLV, churn risk, and recommended strategic actions. Resource allocation must be value-weighted, not volume-driven._
