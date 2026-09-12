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


## 🛠️ Tools & Technologies

| Tool                 | Purpose                                       |
| -------------------- | --------------------------------------------- |
| **Python**           | Data analysis                                 |
| **Pandas**           | Data cleaning, transformation and aggregation |
| **Matplotlib**       | Data visualization                            |
| **Seaborn**          | Statistical visualization                     |
| **Jupyter Notebook** | Analysis environment                          |
| **Git & GitHub**     | Version control and project sharing           |


## 🔍 Data Preparation

The analysis began with exploratory inspection of the dataset structure, data types, categorical variables, missing values, and numerical distributions.

### Data Cleaning Steps

#### 1. Datatype Conversion

`reservation_status_date` was converted from a string to a datetime datatype.

#### 2. Missing Value Analysis

Missing values were identified in:

* `children`
* `country`
* `agent`
* `company`

The notebook identified:

* 4 missing values in `children`
* 488 missing values in `country`
* 16,340 missing values in `agent`
* 112,593 missing values in `company`

#### 3. Removing High-Missing Columns

The `agent` and `company` columns were removed because of their substantial number of missing values.

Remaining missing rows were then removed from the dataset.

#### 4. ADR Outlier Treatment

An ADR box plot was used to inspect extreme values.

The analysis identified an extreme ADR value and filtered the dataset using:

```python
df = df[df['adr'] < 5000]
```

This reduced the analysis dataset from **118,898 to 118,897 rows**.

---

# 📈 Analysis & Findings

## 1. Overall Cancellation Rate

The final dataset contains:

* **74,745 bookings not cancelled**
* **44,152 cancelled bookings**

This results in an overall cancellation rate of:

### **37.13%**

| Booking Status | Bookings | Percentage |
| -------------- | -------: | ---------: |
| Not Cancelled  |   74,745 |     62.87% |
| Cancelled      |   44,152 |     37.13% |

### Key Observation

More than one-third of bookings in the dataset were cancelled, making cancellation behavior an important area for further investigation.


