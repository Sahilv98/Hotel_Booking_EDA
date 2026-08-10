# 🏨 Hotel Booking & Cancellation Analysis

## 📌 Project Overview

This project analyzes **117,853 hotel bookings from 2017–2019** to understand customer booking behaviour, cancellation patterns, hotel popularity, seasonality, and pricing trends.

The analysis was performed using **Python, Pandas, NumPy, Matplotlib, and Seaborn** in Jupyter Notebook.

The project focuses on three core business questions:

1. Which hotel type is booked more often?
2. Does **stay duration** affect the cancellation rate?
3. Does **lead time** affect the cancellation rate?

The objective is to transform raw hotel booking data into **actionable business insights and recommendations** that can help hotels improve revenue management and reduce cancellation-related losses.

---

## 🎯 Business Objective

The primary objective is to identify the factors associated with hotel booking cancellations and understand demand patterns across **City Hotel** and **Resort Hotel**.

The analysis aims to support business decisions related to:

* Cancellation policy
* Advance booking management
* Deposit and confirmation strategies
* Seasonal pricing
* Customer segmentation
* Revenue protection
* Demand and capacity planning

---

## 📊 Dataset

The original dataset contains approximately **119K hotel bookings and 29 columns**, covering the period **2017–2019**.

After data cleaning and preprocessing, the final analytical dataset contains:

* **117,853 bookings**
* **26 columns**

### Important Variables

| Variable                  | Description                                |
| ------------------------- | ------------------------------------------ |
| `hotel`                   | Type of hotel — City Hotel / Resort Hotel  |
| `is_canceled`             | Booking cancellation status                |
| `lead_time`               | Number of days between booking and arrival |
| `stays_in_weekend_nights` | Weekend nights stayed                      |
| `stays_in_week_nights`    | Weekday nights stayed                      |
| `adr`                     | Average Daily Rate                         |
| `deposit_type`            | Deposit type associated with the booking   |
| `market_segment`          | Booking market segment                     |
| `is_repeated_guest`       | Whether the guest is a repeat customer     |
| `arrival_date_month`      | Arrival month                              |
| `meal`                    | Meal plan selected                         |

---

## 🧹 Data Preprocessing

Several data-quality issues were addressed before performing the analysis.

### Major preprocessing steps

* Handled missing values in relevant columns.
* Converted the `children` column to an appropriate numeric type.
* Filled missing agent values with `0`.
* Replaced missing city values with `"Unknown"`.
* Combined arrival year, month and day into a proper date field.
* Removed invalid negative ADR values.
* Removed an extreme ADR outlier.
* Removed bookings with zero guests.
* Recategorised `"Undefined"` meal values as `"Self-Catering"`.
* Reviewed duplicate records and retained them where identical records could represent separate bookings.

After preprocessing, the dataset was reduced from **119,390 to 117,853 valid analytical records**.

---

## 🔎 Exploratory Data Analysis

The project contains multiple visualisations covering booking volume, cancellations, pricing, customer behaviour and seasonality.

### 1. Hotel Type Popularity

**City Hotel** accounts for approximately **66.5% of bookings**, while **Resort Hotel** accounts for approximately **33.5%**.

This shows that City Hotel is the dominant booking destination in the dataset.

---

### 2. Cancellation by Hotel Type

City Hotel has a significantly higher cancellation rate:

| Hotel Type   | Cancellation Rate |
| ------------ | ----------------: |
| City Hotel   |        **41.80%** |
| Resort Hotel |        **27.81%** |

This indicates that City Hotel has a considerably higher cancellation exposure than Resort Hotel.

---

### 3. Stay Duration vs Cancellation

Cancellation rates increase as the total length of stay increases.

For City Hotel:

* **1–3 nights:** 42.75%
* **15+ nights:** 76.82%

For Resort Hotel:

* **1–3 nights:** 23.79%
* **15+ nights:** 45.13%

The relationship is therefore **positive** — longer stays are associated with higher cancellation rates.

---

### 4. Lead Time vs Cancellation

Lead time shows one of the strongest relationships with cancellation behaviour.

For City Hotel:

* **0–30 days:** 22.28%
* **365+ days:** 70.92%

For Resort Hotel:

* **0–30 days:** 12.83%
* **365+ days:** 46.62%

As bookings are made further in advance, cancellation risk increases substantially.

---

### 5. Seasonal Booking Trends

City Hotel maintains higher booking volumes throughout the year.

Resort Hotel shows stronger seasonality, with booking activity increasing around the summer/autumn period.

**October** is one of the strongest booking months for both hotel types.

---

### 6. Seasonal ADR Analysis

Resort Hotel demonstrates significantly stronger seasonal pricing behaviour.

Its ADR increases sharply around **September–October**, reaching approximately **187 in October**.

This indicates strong pricing power during the peak seasonal period.

---

### 7. Market Segment Analysis

Some booking segments show particularly high cancellation risk.

At City Hotel:

* **Groups:** 68.85%
* **Offline TA/TO:** 43.01%

These segments therefore represent important targets for more controlled booking policies.

---

### 8. Repeat vs First-Time Guests

Repeat guests demonstrate considerably lower cancellation behaviour:

| Guest Type       | Cancellation Rate |
| ---------------- | ----------------: |
| First-Time Guest |        **37.84%** |
| Repeat Guest     |        **14.64%** |

This suggests that repeat customers represent a relatively more reliable booking segment.

---

## 💡 Key Business Insights

### Insight 1 — City Hotel dominates booking volume

City Hotel receives approximately two-thirds of all bookings, making it the primary demand driver.

### Insight 2 — City Hotel also carries greater cancellation risk

Across several dimensions, City Hotel consistently records higher cancellation rates than Resort Hotel.

### Insight 3 — Longer stays have greater cancellation exposure

Cancellation rates increase with stay duration, particularly for City Hotel.

### Insight 4 — Advance bookings are high-risk

The further in advance a booking is made, the greater the probability of cancellation.

### Insight 5 — Resort Hotel has stronger seasonal pricing power

Resort Hotel's ADR rises significantly during September–October, indicating an opportunity for demand-based pricing.

### Insight 6 — Repeat guests are more reliable

Repeat guests have a substantially lower cancellation rate than first-time guests.

---

## 🚀 Business Recommendations

### 1. Strengthen policies for high-risk City Hotel segments

Groups and Offline TA/TO bookings show significantly higher cancellation rates at City Hotel.

Hotels should consider:

* Partial deposits
* Stricter confirmation policies
* Graduated cancellation fees
* Closer booking monitoring

---

### 2. Introduce differentiated policies for long-lead bookings

Bookings made far in advance should receive additional confirmation mechanisms.

Possible actions include:

* Confirmation reminders
* Partial deposits
* Flexible rescheduling options
* Graduated cancellation charges

---

### 3. Apply stronger controls to longer stays

Longer bookings carry higher cancellation exposure.

Hotels could consider:

* Minimum-stay policies
* Partial deposits
* Stay-length-based cancellation fees
* Special confirmation requirements

---

### 4. Investigate the Non Refund anomaly

Non Refund bookings show an unusually high **99.37% cancellation rate**.

This is counter-intuitive and should be investigated before using this category as evidence of effective cancellation protection.

Possible explanations could include operational booking practices, agent/wholesaler holds or booking-status conventions.

---

### 5. Leverage Resort Hotel seasonality

Resort Hotel shows strong pricing power during September–October.

The hotel can use:

* Dynamic pricing
* Premium seasonal rates
* Promotional packages during shoulder periods
* Capacity optimisation during peak months

Similar pricing strategies could also be tested at City Hotel during its strongest demand periods.

---

## ⭐ Highest-Impact Recommendation

### Focus on long-lead-time bookings.

Lead time shows the **strongest and most consistent relationship with cancellation behaviour** across both hotel types.

City Hotel cancellation increases from:

**22.28% → 70.92%**

when moving from **0–30 days** to **365+ days** of lead time.

Therefore, a **risk-based cancellation policy** can be introduced:

> Short lead time → Standard terms
> Medium lead time → Confirmation reminder
> Long lead time → Deposit + stronger confirmation
> Very long lead time → Strict cancellation/rescheduling terms

This approach directly targets the most significant cancellation-risk pattern identified in the analysis.

---

## 🛠️ Tools & Technologies

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**

---

## 📁 Project Structure

```text
Hotel-Booking-EDA/
│
├── 📓 hotel_booking_EDA.ipynb
│
├── 📊 hotel_bookings.csv
│
├── 📄 hotel_business_eda_report.pdf
│
├── 📄 hotel_business_project.pdf
│
└── README.md
```

> The dataset file can be omitted from the repository if it is too large or subject to dataset licensing restrictions. In that case, provide the original dataset source separately.

---

## 📈 Project Workflow

```text
Raw Hotel Booking Data
        │
        ▼
Data Loading
        │
        ▼
Data Quality Assessment
        │
        ▼
Data Cleaning & Preprocessing
        │
        ▼
Feature Creation
        │
        ▼
Exploratory Data Analysis
        │
        ├── Hotel Type Analysis
        │
        ├── Monthly Booking Analysis
        │
        ├── Cancellation Analysis
        │
        ├── Stay Duration Analysis
        │
        ├── Lead Time Analysis
        │
        ├── Market Segment Analysis
        │
        └── ADR & Seasonality Analysis
        │
        ▼
Business Insights
        │
        ▼
Recommendations
        │
        ▼
Business Conclusion
```

---

## 📌 Final Conclusion

The analysis of **117,853 hotel bookings** shows that City Hotel is more popular but has substantially higher cancellation risk than Resort Hotel.

Cancellation risk increases with both **stay duration and lead time**, with City Hotel showing the sharpest increase.

Resort Hotel, on the other hand, demonstrates stronger seasonal demand and pricing power, particularly around September–October.

Overall, the analysis suggests that hotels can reduce revenue leakage by implementing **risk-based cancellation policies**, particularly for **long-lead-time, long-stay and high-risk City Hotel bookings**, while using seasonal pricing strategies to maximise revenue during peak demand periods.

---

## 👤 Author

**Sahil Verma**

Aspiring Data Scientist | Data Analytics | Python | SQL | Power BI

---

## ⭐ If you found this project useful

Feel free to ⭐ the repository and explore the Jupyter Notebook for the complete analysis and visualisations.
