# 🏨 HotelStay – Hotel Booking Analysis Dashboard

An interactive **Hotel Booking Analysis Dashboard** built using Microsoft Power BI to analyze hotel bookings, cancellations, estimated revenue, booking channels, and guest behavior across City Hotel and Resort Hotel.

## 📌 Project Overview

HotelStay transforms raw hotel booking data into an interactive, four-page Power BI dashboard. The project focuses on identifying booking trends, understanding cancellation patterns, comparing hotel performance, and discovering opportunities to improve direct bookings and guest retention.

The analysis covers **119,390 raw records**, reduced to **87,389 records after data cleaning**.

## 🎯 Project Objectives

- Analyze hotel booking and cancellation patterns.
- Compare the performance of City Hotel and Resort Hotel.
- Evaluate estimated revenue and Average Daily Rate (ADR).
- Identify high-performing booking channels and market segments.
- Understand guest behavior, stay duration, and repeat bookings.
- Build an interactive dashboard with KPIs, charts, and slicers.
- Provide data-driven business recommendations.

## 🛠️ Tools & Technologies

- **Microsoft Power BI Desktop** – Dashboard development and visualization
- **Power Query** – Data cleaning and transformation
- **DAX** – KPI calculations and analytical measures
- **Data Modeling** – Organizing and analyzing booking data
- **Kaggle** – Dataset source

## 📂 Dataset Information

| Attribute | Details |
|---|---|
| Dataset | `hotel_bookings.csv` |
| Source | Kaggle |
| Hotels | City Hotel and Resort Hotel |
| Raw records | 119,390 |
| Records after cleaning | 87,389 |
| Original columns | 32 |
| Arrival period | July 2015 – August 2017 |

The dataset includes booking status, lead time, arrival dates, length of stay, guest details, meal plans, market segments, distribution channels, room types, deposit types, and average daily rates.

## 🧹 Data Cleaning & Preparation

Data preparation was performed in Power Query.

- Checked missing values in company, agent, country, and children columns.
- Removed unused columns, including the mostly empty company column.
- Replaced missing agent values with `0`, country values with `Unknown`, and children values with `0`.
- Removed blank rows and exact duplicate rows.
- Trimmed and cleaned text columns.
- Corrected data types for numerical, decimal, and date columns.
- Created custom columns for total nights, total guests, estimated revenue, room changes, and month numbers.
- Sorted months in calendar order for accurate trend analysis.

## 📊 Dashboard Pages

### 1. Overview
- Total bookings and estimated revenue
- Average Daily Rate (ADR)
- Cancellation rate and average stay
- Monthly booking trends
- Booking distribution by hotel
- Revenue by year
- Top 10 countries by bookings

### 2. Booking Analysis
- Total bookings, guests, and confirmed bookings
- Monthly booking trends by hotel
- Bookings by market segment
- Hotel performance summary table
- Comparison of revenue, ADR, average stay, lead time, and cancellations

### 3. Cancellation Analysis
- Overall cancellation rate and cancelled bookings
- Cancellation rates by deposit type
- Cancellation patterns by customer type
- Cancellation comparison between City Hotel and Resort Hotel
- Cancellation rates across market segments

### 4. Guest Analysis
- Total guests and repeat guest bookings
- Average length of stay
- Bookings by distribution channel
- Reserved versus assigned room types
- Bookings by meal plan

**Interactive features:** Hotel and year slicers are available on every dashboard page, along with page navigation buttons.

## 📈 Key Insights

- **87,389 bookings** remained after data cleaning.
- **27.49% cancellation rate**, representing approximately 24,025 cancelled bookings.
- **$22.98 million estimated revenue** from bookings that were not cancelled, based on the project's revenue calculation.
- City Hotel contributed **61.14% of bookings**, while Resort Hotel contributed 38.86%.
- City Hotel recorded a higher average daily rate of approximately **$108**, compared with $93 for Resort Hotel.
- Resort Hotel guests stayed longer on average: **4.20 nights**, compared with 2.99 nights at City Hotel.
- August was the peak booking month for both hotels.
- Online Travel Agents (Online TA) represented the largest market segment, with approximately 52,000 bookings.
- The cancellation rate for Online TA bookings was **35.35%**, compared with 14.72% for Direct bookings.
- Approximately 15% of bookings involved a room different from the room originally reserved.
- Portugal was the leading country by booking volume, followed by the UK, France, Spain, and Germany.

*Note: Revenue is an estimate calculated using ADR multiplied by total nights for non-cancelled bookings. It does not represent verified actual payments. The unusually high cancellation rate for non-refundable deposits should be validated before drawing business conclusions.*

## 💡 Business Recommendations

- **Increase direct bookings:** Introduce member-only rates and website booking incentives.
- **Reduce cancellations:** Use booking reminders and communicate deposit policies clearly, especially for bookings made well in advance.
- **Validate deposit data:** Investigate the unusually high cancellation rate associated with non-refundable deposits.
- **Improve guest retention:** Develop loyalty programs and offers for returning guests.
- **Increase longer stays:** Explore extended-stay packages for City Hotel.
- **Prepare for seasonal demand:** Plan staffing and inventory for peak booking periods, particularly August.
- **Improve room allocation:** Investigate why some guests receive a different room from the one reserved.

## 🧮 Key DAX Measures

The project includes measures for booking performance, cancellations, revenue, and guest behavior.

```dax
Total Bookings =
COUNTROWS(hotel_bookings)

Confirmed Bookings =
CALCULATE(
    [Total Bookings],
    hotel_bookings[is_canceled] = 0
)

Cancelled Bookings =
CALCULATE(
    [Total Bookings],
    hotel_bookings[is_canceled] = 1
)

Cancellation Rate =
DIVIDE(
    [Cancelled Bookings],
    [Total Bookings]
)

Total Revenue =
SUM(hotel_bookings[Revenue])

Avg Lead Time =
AVERAGE(hotel_bookings[lead_time])

Avg Special Requests =
AVERAGE(hotel_bookings[total_of_special_requests])
```

Additional measures include total guests, average stay, average ADR, repeat guest percentage, room change percentage, room nights sold, ADR per room night, and revenue per confirmed booking.

## 📁 Project Structure

```text
HotelStay-Hotel-Booking-Analysis/
│
├── README.md
├── hotel_bookings.csv
├── Hotel_Booking_Dashboard_Report.docx
└── HotelStay_Dashboard.pbix
```

*The filenames above are suggested for organizing your GitHub repository. Include only the files you actually upload.*

## 🚀 Skills Demonstrated

- Data Cleaning & Transformation
- Exploratory Data Analysis
- Power Query
- DAX Measures & Calculated Columns
- Data Modeling
- KPI Development
- Interactive Dashboard Design
- Business Intelligence & Data Storytelling
- Analytical Insights & Business Recommendations

## 🏁 Conclusion

The HotelStay project demonstrates an end-to-end business intelligence workflow, from data cleaning and transformation to DAX calculations and interactive reporting. The dashboard highlights differences in hotel performance, booking channels, cancellation behavior, and guest preferences, providing actionable insights to support better booking management and customer retention.

## 👩‍💻 Author

**Shyamala Devi N**

- GitHub: [Visit My GitHub Profile](https://github.com/yogitha0406)
- LinkedIn: [Connect with Me](https://www.linkedin.com/in/yogitha-devi/)

---

*Developed using Microsoft Power BI Desktop.*
