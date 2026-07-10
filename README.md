# Hotel Booking Cancellation Analysis

Excel-based end-to-end data analysis project exploring the drivers of booking cancellations across ~119,000 hotel reservations, translating raw transactional data into an interactive dashboard and actionable business recommendations.

## Objective

Hotel cancellations create significant revenue uncertainty and operational waste (unsold rooms, misallocated staffing). This project analyzes historical booking data to:
- Identify the strongest predictors of cancellation
- Quantify cancellation risk across customer segments, booking channels, and hotel types
- Translate findings into concrete, actionable recommendations to reduce avoidable cancellations

## Dataset

- **Source:** Hotel Booking Demand dataset (City Hotel & Resort Hotel)
- **Size:** 119,209 bookings, 35 columns (pre-cleaning: 32 original + 3 engineered), arrival dates spanning 2015–2017
- **Fields:** booking details (lead time, stay length, deposit type, market segment), guest profile (adults/children/babies, repeat guest status, customer type), and outcome (`is_canceled`)

## Tools

- **Microsoft Excel**: PivotTables & PivotCharts, Slicers, formula-based feature engineering (`IF`, `DATE`, nested logic), dashboard design (KPI cards, chart layout, cross-filtering)

## Process

1. **Data Cleaning & Preparation**
   - Audited missing values (`company` 94% NULL → dropped; `agent` 13.7% NULL; `children` 0.3% NULL → filled with 0)
   - Removed invalid records: bookings with 0 total guests, negative ADR
   - Retained ADR = 0 and length_of_stay = 0 records after confirming they likely represent legitimate promotional/day-use bookings rather than data errors
   - Investigated suspicious patterns: bookings with lead time > 365 days (2.64% of data) showed a cancellation rate of 67.7% vs. 36.0% baseline
   - Flagged a data-entry anomaly: 24 bookings with 0 adults/children/babies, all canceled, mostly City Hotel

2. **Feature Engineering**
   - `month_year`, `total_guests`, `length_of_stay`, `has_cancel_history`, `room_changed`, `group_lead_time` (lead time bucketed into 0–30 / 31–90 / 91–180 / 181–365 / >365 days for business interpretability)

3. **Exploratory Data Analysis**
   - Hypothesis-driven EDA across four dimensions: Lead Time, Deposit Type, Market Segment, and Prior Cancellation History

4. **PivotTable Analysis**
   - Cross-tabulated cancellation rate by lead time, deposit type, market segment, distribution channel, hotel type, customer type, and time period (year/quarter/month)

5. **Dashboard Design**
   - **Overview Dashboard**: KPI summary (Total Bookings, Canceled Bookings, Cancellation Rate, Avg. Lead Time) + monthly trend and hotel-type comparison charts, filterable by year/hotel type
   - **Cancellation Risk Analysis Dashboard**: deep-dive charts on market segment, lead time, distribution channel, prior cancellation history, and customer type

6. **Insights & Recommendations**
   - Synthesized findings into a business-facing summary pairing each insight with a targeted, actionable recommendation

## Key Insights

| # | Insight | Metric |
|---|---------|--------|
| 1 | Prior cancellation history is the strongest predictor of future cancellation | 91.7% (history) vs. 33.9% (no history) |
| 2 | Long lead time bookings carry substantially higher cancellation risk | 67.7% cancellation rate for lead time > 365 days |
| 3 | Group bookings are the highest-risk market segment | 61.1% cancellation rate |
| 4 | Lead time risk is more pronounced for City Hotel than Resort Hotel | 71.1% (City) vs. 46.6% (Resort) at lead time > 365 days |

Additional notable pattern: bookings under a "Non-Refund" deposit type show a near-total cancellation rate (99.4%), an anomaly worth further investigation (possible speculative or fraudulent bookings rather than genuine no-deposit trust behavior).

## Recommendations

- **High-risk customer monitoring**: CRM flag + personalized reminders + partial deposit requirement for guests with prior cancellations
- **Long lead-time booking management**: staged confirmation reminders (30/14/7 days) and flexible rescheduling options
- **Group booking policy**: require partial deposits and confirmed headcounts to reduce speculative group holds
- **Differentiated cancellation policy by hotel type**: apply stricter terms for long lead-time City Hotel bookings, given their disproportionately higher cancellation risk

## Deliverables

- `Project_Hotel_Bookings.xlsx` — full workbook (raw data, cleaning log, EDA, PivotTables, 2 interactive dashboards, insights & recommendations)
- This README

## Author

Nguyen Le Duc Tri — Data Analyst
