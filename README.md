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

## Data Overview

**Dataset:** [Online Retail II dataset](https://archive.ics.uci.edu/dataset/502/online+retail+ii) from UCI Machine Learning Repository

**Coverage:** 1,067,371 transaction records | December 2009 - December 2011 | 41 countries

**After cleaning:** 805,549 valid transactions from 5,942 unique customers

**Data Preparation:**

- Removed 23% of transactions missing Customer IDs (non-registered purchases)
- Filtered cancellations and returns (negative quantities/prices)
- Aggregated line-items to customer-transaction level
- Created RFM metrics for segmentation

3. **Resource Allocation:** How should pricing, discounts, and retention investments be differentiated by customer segment to maximize ROI?

The analysis constructs a framework linking **segmentation → lifetime value → pricing strategy**, enabling efficient allocation of retention spend and pricing flexibility aligned with customer behavior rather than arbitrary rules.

