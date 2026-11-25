# Hotel Booking & Cancellation Analysis (Excel)

An end-to-end Excel analysis of hotel booking data for a City Hotel and a Resort Hotel. The project covers data cleaning, formula-based analysis, pivot tables and a dashboard, and answers 8 business questions about booking performance and cancellations.

## Project Overview

Cancellations cost hotels revenue and make demand harder to plan. This project looks at **what drives bookings and cancellations** and suggests practical ways for hotel management to reduce cancellations and improve booking performance.

- **Tool:** Microsoft Excel
- **Techniques:** data cleaning, `COUNTIF` / `COUNTIFS` / `AVERAGEIF`, calculated columns, pivot tables, charts, dashboard design
- **Dataset:** [Hotel Booking Demand Dataset – Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (public dataset, July 2015 to August 2017)
- **Size:** 119,390 raw rows, 87,396 rows after cleaning

## Workbook Structure

| Sheet | Purpose |
|---|---|
| `Raw_Data` | Original, untouched dataset |
| `Cleaned_Data` | Cleaned dataset used for all analysis (adds `total_guests` and `total_nights`) |
| `Data_Quality_Summary` | Log of every data issue found, the action taken and the reason |
| `Analysis` | Answers to the 8 business questions, with tables and insights |
| `Pivot Tables` | Pivot tables for hotel type, month, market segment, country and cancellations |
| `Dashboard` | KPI cards, hotel comparison, monthly trend chart and key insights |

## Data Cleaning

| Issue | Count | Action |
|---|---|---|
| Duplicate rows | 31,994 | Removed |
| Missing children | 4 | Replaced with 0 |
| Missing country | 452 | Replaced with "Unknown" |
| Missing agent | 12,193 | Replaced with "Not Assigned" |
| Missing company | 82,137 | Replaced with "Not Provided" |
| Negative ADR | 1 | Value cleared (left blank, not assumed to be 0) |
| Zero-guest bookings | 166 | Retained |
| Lead time above 365 days | 565 | Retained (unusual but possible) |
| ADR above 500 | 3 | Retained |

Two calculated columns were added: `total_guests` (adults + children + babies) and `total_nights` (weekend + week nights).

## Business Questions & Key Findings

### 1. How do City and Resort hotels compare?

| Metric | City Hotel | Resort Hotel |
|---|---|---|
| Total bookings | 53,428 | 33,968 |
| Cancellation rate | 30.04% | 23.48% |
| Average ADR | 110.99 | 99.03 |
| Average length of stay | 3.15 nights | 4.39 nights |

City Hotels get more bookings and a higher ADR. Resort Hotels have fewer cancellations and longer stays.

### 2. What percentage of bookings are cancelled?

27.49% of all bookings (24,025 of 87,396).

### 3. Which months receive the most bookings?

August (11,257) and July (10,057) are highest, and January (4,693) is lowest. Note: the data covers July 2015 to August 2017, so July and August include three years of data while the other months include two.

### 4. Which market segment generates the most bookings?

Online TA (Travel Agents) with 51,618 bookings, about 59% of the total.

### 5. Does lead time relate to cancellations?

Yes. The cancellation rate rises steadily with lead time, from **16.42%** (0–30 days) to **40.88%** (over 365 days).

### 6. Which countries contribute the most bookings?

Portugal (27,453), then the United Kingdom (10,433) and France (8,837).

### 7. Which customer types cancel the most?

Transient customers (30.11%). Group customers cancel the least (9.93%).

### 8. What can management do?

| Finding | Recommendation |
|---|---|
| City Hotels have a higher cancellation rate | Introduce stricter cancellation policies where appropriate |
| Longer lead times lead to more cancellations | Send booking reminders and offer incentives for early confirmation |
| Online TA generates the most bookings | Strengthen partnerships with online travel agencies, but negotiate stricter cancellation terms, since they drive volume but also most cancellations |
| Transient customers cancel the most | Introduce targeted confirmation and retention strategies |

## Limitations & Next Steps

- **Seasonality:** monthly totals are raw counts across the full dataset and are not adjusted for the uneven number of years per month.
- **Average ADR** includes cancelled bookings and bookings with an ADR of 0 (for example complimentary stays), so it is not a measure of realised revenue.
- **Cancellations** include no-shows.
- **Lead time and cancellations** show an association, not proof of cause.
- **Next steps:** analyse cancellation rate by market segment (Online TA appears to drive a large share of cancellations), add estimated revenue (ADR × nights for non-cancelled bookings), and compare performance year over year.

## How to Use

1. Download the workbook and open it in Excel.
2. Start with the `Dashboard` sheet for a summary.
3. Go to `Analysis` for the detailed answer to each business question.
4. Check `Data_Quality_Summary` to see how the data was cleaned.

All analysis tables use live formulas on `Cleaned_Data`, so they update if the data changes.

## Author

**ROHIT BHATT**

[LinkedIn](https://www.linkedin.com/in/rohitbhatt-lnkd/) | [GitHub](https://github.com/Rohitbhatt0407) | [Email](mailto:Rohitbhatt0407@gmail.com)
