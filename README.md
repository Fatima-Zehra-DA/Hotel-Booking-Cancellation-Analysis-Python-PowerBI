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


## Assumptions

1.	No unusual occurrences between 2015 and 2017 will have a substantial impact on
1.	the data used.
2.	The information is still current and can be used to analyze a hotel's possible plans in
3.	an efficient manner.
4.	There are no unanticipated negatives to the hotel employing any advised technique.
5.	The hotels are not currently using any of the suggested solutions.
6.	The biggest factor affecting the effectiveness of earning income is booking
7.	cancellations.
8.	6. Cancellations result in vacant rooms for the booked length of time.
9.	7. Clients make hotel reservations the same year they make cancellations.

## Research Question
1.	What are the key factors associated with hotel booking cancellations?
2.	How can hotels reduce booking cancellations and improve room occupancy and revenue?
3.	How can the findings help hotels make better pricing and promotional decisions?
4.	What is the overall cancellation rate, and how does it differ between City Hotel and Resort Hotel? 
5.	How does cancellation rate vary with lead time? 
6.	How does cancellation rate vary by deposit type? 
7.	Which booking channels and market segments have the highest cancellation rates? 
8.	What types of customers are most likely to cancel their reservations?



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

