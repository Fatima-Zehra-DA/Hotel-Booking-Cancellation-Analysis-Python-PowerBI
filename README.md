# 🏨 Hotel Booking Cancellation Analysis | Python

An exploratory data analysis project focused on understanding **hotel booking cancellation patterns** using Python.

The analysis examines how cancellation rates vary across **hotel types, lead time, deposit types, distribution channels, and market segments**, with additional investigation into the unusually high cancellation rate observed for **Non Refund bookings**.

The goal is to move beyond overall cancellation percentages and identify patterns that could help hotels better understand cancellation risk.

## 📌 Project Overview

Hotel cancellations can affect room availability, planning, and operational decision-making.

In this project, I used **Python, Pandas, Matplotlib, and Seaborn** to explore a hotel bookings dataset and answer questions such as:

* What proportion of bookings are cancelled?
* Does cancellation behavior differ between City and Resort Hotels?
* How does lead time relate to cancellation rates?
* How does cancellation rate vary by deposit type?
* Which booking channels show higher cancellation rates?
* How do cancellation patterns differ across market segments?
* Why is the cancellation rate for **Non Refund bookings** unusually high?

The analysis follows an exploratory approach, using summary tables and visualizations to identify patterns and areas requiring deeper investigation.

## 🎯 Objectives

* Measure the overall hotel booking cancellation rate.
* Compare cancellation rates between **City Hotel** and **Resort Hotel**.
* Analyze cancellation behavior across different **lead-time groups**.
* Compare cancellation rates by **deposit type**.
* Investigate the unusually high cancellation rate for **Non Refund** bookings.
* Examine cancellation patterns across **distribution channels**.
* Analyze cancellation rates across **market segments**.
* Translate analytical findings into practical business observations.

## 📊 Dataset

The dataset contains hotel booking records with information about:

* Hotel type
* Booking status
* Lead time
* Arrival dates
* Length of stay
* Guest information
* Market segment
* Distribution channel
* Previous cancellations
* Room types
* Deposit type
* Customer type
* Average Daily Rate (ADR)
* Special requests
* Reservation status

### Dataset Size

| Stage                                                   |    Rows | Columns |
| ------------------------------------------------------- | ------: | ------: |
| Original dataset                                        | 119,390 |      32 |
| After removing `agent` and `company` and missing values | 118,898 |      30 |
| Final analysis dataset after ADR outlier removal        | 118,897 |      30 |

The notebook shows that the original dataset contains **119,390 rows and 32 columns**.

### Data Privacy

The working dataset used for this project contains **32 columns** and does not include personally identifying guest fields such as names, email addresses, phone numbers, or credit-card information.

The dataset is therefore used strictly for analytical and educational purposes.
