# Hotel Booking Cancellation Analysis (Excel Dashboard)

## Project Overview

Booking cancellations have a significant impact on hotel operations, leading to revenue loss, inefficient resource allocation, and inaccurate occupancy planning.

This project analyzes hotel booking data to identify the major factors influencing booking cancellations and provides actionable business recommendations through an interactive Excel dashboard.

Instead of using Power BI, this project was intentionally built entirely in Microsoft Excel to simulate a real business environment where hotel managers primarily rely on Excel for operational reporting and may not have access to BI platforms.

---

## Business Challenge

The hotel management team needed an interactive reporting solution to monitor booking cancellations and identify key cancellation drivers.

However:

- Business users primarily use Microsoft Excel.
- Power BI licenses are not available for all users.
- The dataset (~120,000 booking records) is manageable within Excel.
- The solution must be easy to share, maintain, and use without technical expertise.

The challenge was to build a self-service analytical dashboard entirely in Excel while still delivering meaningful business insights.

---

## Objectives

- Analyze booking cancellation behavior.
- Identify the major drivers behind cancellations.
- Compare cancellation patterns across hotel types and customer segments.
- Provide actionable recommendations to reduce future cancellations.
- Build an interactive Excel dashboard for business users.

---

## Dataset

**Source:** Hotel Booking Demand Dataset (Kaggle)

- 119,390 booking records
- 32 original variables
- City Hotel & Resort Hotel
- Booking period: 2015–2017

---

## Tools

- Microsoft Excel
- Pivot Tables
- Pivot Charts
- Slicers
- Conditional Formatting
- Excel Formulas

---

## Project Workflow (CRISP-DM)

### 1. Business Understanding

- Defined business objectives
- Proposed cancellation hypotheses
- Identified KPIs

### 2. Data Understanding

- Explored dataset structure
- Profiled variables
- Investigated missing values and anomalies

### 3. Data Preparation

- Removed invalid guest records
- Treated missing values
- Checked duplicates
- Created engineered features:
  - Arrival Date
  - Total Guests
  - Length of Stay
  - Lead Time Group
  - Room Changed
  - Has Cancel History

### 4. Exploratory Data Analysis

Analyzed cancellation behavior by:

- Lead Time
- Market Segment
- Distribution Channel
- Customer Type
- Previous Cancellation History
- Hotel Type

---

## Dashboard

### Overview Dashboard

- Total Bookings
- Cancelled Bookings
- Cancellation Rate
- Average Lead Time
- Booking Trend
- Hotel Comparison

Provides a real-time snapshot of overall cancellation performance:

- **KPI cards** - 119,209 total bookings, 44,199 cancellations, a 37.08% overall cancellation rate, and an average lead time of 104 days.
- **Booking Trend chart** - cancellation rate fluctuates seasonally rather than trending steadily up or down, with noticeably higher cancellation months around mid-year (e.g. July) and lower cancellation in November, suggesting a seasonal booking-behavior pattern worth factoring into staffing/inventory planning.
- **Hotel Comparison chart** - City Hotel consistently cancels at a higher rate than Resort Hotel (41.8% vs 27.8%), indicating the two properties may need different retention strategies.

![Dashboard](https://github.com/user-attachments/assets/7ff59a0d-33c9-4d9d-8f57-801b7c517efc)

### Cancellation Risk Dashboard

- Lead Time Analysis
- Market Segment
- Customer Type
- Distribution Channel
- Previous Cancellation History

Breaks down cancellation risk across the dimensions that matter most for targeting interventions:

- **Lead Time Analysis** - risk increases steadily with booking window, from 18.6% (0–30 days) to 67.7% (>365 days).
- **Market Segment** - Groups (61.1%) and Online TA (36.8%) are the highest-risk channels, while Complementary (12.2%) and Direct (15.4%) are the safest.
- **Customer Type & Cancellation History** - repeat cancelers are ~2.7x more likely to cancel again (91.7% vs 33.9%), making this the single strongest individual risk signal in the dataset.

![Dasboard](https://github.com/user-attachments/assets/374221ed-640a-446d-994f-816e48b2952e)

Interactive filtering is supported using Excel Slicers.

---

## Key Insights

### Previous cancellation history is the strongest predictor.

Customers with previous cancellations were nearly **3× more likely** to cancel again (91.68% vs. 33.94%).

---

### Long lead times increase cancellation risk.

Bookings made over one year in advance reached a cancellation rate of **67.65%**.

---

### Group bookings have the highest cancellation rate.

The **Groups** market segment recorded a **61.11%** cancellation rate.

---

### City Hotels are more sensitive to long lead times.

For bookings made more than one year in advance:

- City Hotel: 71.11%
- Resort Hotel: 46.62%

---

## Business Recommendations

- Monitor high-risk customers with previous cancellation history.
- Implement reminder campaigns for long lead-time bookings.
- Require partial deposits for group bookings.
- Apply different cancellation policies for City Hotels and Resort Hotels.

---

## Deliverables

- Excel Dashboard
- Data Preparation Documentation
- EDA Report
- Business Insights
- Strategic Recommendations

---

## Project Structure

```
├── Data Preparation
├── EDA
├── Pivot Tables
├── Dashboard
├── Insight & Recommendation
└── README.md
```

---

## Future Improvements

- Build a cancellation prediction model using Machine Learning.
- Estimate revenue loss caused by cancellations.
- Perform customer segmentation.
- Develop cancellation risk scoring.

---

## Author
Nguyen Le Duc Tri - Data Analyst
