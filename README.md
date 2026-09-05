# Hotel Booking Cancellation Analysis | Python | Power BI

## Project Status
🚧 In Progress

## Overview

This project analyzes hotel booking cancellations to identify
patterns and factors associated with cancellation behavior.

## Business Problem
In recent years, City Hotel and Resort Hotel have seen high cancellation rates. Each
hotel is now dealing with a number of issues as a result, including fewer revenues and
less than ideal hotel room use. Consequently, lowering cancellation rates is both hotels'
primary goal in order to increase their efficiency in generating revenue, and for us to
offer thorough business advice to address this problem.
The analysis of hotel booking cancellations as well as other factors that have no bearing
on their business and yearly revenue generation are the main topics of this report.



## Business Questions

- What factors are associated with hotel booking cancellations?
- How does cancellation rate vary by hotel type?
- How does cancellation rate vary with lead time?
- How does cancellation rate vary by deposit type?
- Which booking channels and market segments have higher cancellation rates?

## Dataset

This project uses the publicly available **Hotel Booking Demand** dataset.

**Source:** Kaggle — Hotel Booking Demand Dataset

**Original dataset:** [https://www.kaggle.com/datasets/mojtaba142/hotel-booking]

### Dataset Preparation

The original dataset contains **119,390 records and 36 columns**.

Before analysis, the following four columns were excluded because they were not required for the business questions:

* `name`
* `email`
* `phone-number`
* `credit_card`

After excluding these columns, the analysis was performed using **119,390 records and 32 columns**.

> **Note:** The dataset was not uploaded to this repository. Please download the original dataset from the source above if you want to reproduce the analysis.


## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Current Progress

- [x] Data exploration
- [x] Overall cancellation rate
- [x] Cancellation rate by hotel type
- [x] Cancellation rate by lead time
- [x] Cancellation rate by deposit type
- [ ] Investigate Non Refund cancellation anomaly
- [ ] Cancellation rate by market segment
- [ ] Cancellation rate by booking channel
- [ ] Customer-level analysis
- [ ] Business recommendations
- [ ] Final report

## Key Finding So Far

Non Refund bookings show an exceptionally high cancellation rate
of 99.36%, which is being investigated further before drawing
business conclusions.

## Project Status

This project is currently under development.

