# 🏨 Hotel Booking Cancellation Analysis | Python

An exploratory data analysis project focused on understanding **hotel booking cancellation patterns** using Python.

The analysis examines how cancellation rates vary across **hotel types, lead time, deposit types, distribution channels, and market segments**, with additional investigation into the unusually high cancellation rate observed for **Non Refund bookings**.

The goal is to move beyond overall cancellation percentages and identify patterns that could help hotels better understand cancellation risk.

## Project Status
🚧 In Progress

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


---

## 2. Cancellation Rate by Hotel Type

Cancellation rates differ noticeably between the two hotel types:

| Hotel Type   | Cancellation Rate |
| ------------ | ----------------: |
| City Hotel   |        **41.71%** |
| Resort Hotel |        **27.98%** |

The difference is **13.73 percentage points**.

### Key Observation

**City Hotel bookings have a substantially higher cancellation rate than Resort Hotel bookings.**

This suggests that cancellation behavior may be influenced by the type of hotel, although this analysis alone does not establish why the difference exists.

---

## 3. Cancellation Rate by Lead Time

Lead time was grouped into:

* **0–7 days**
* **8–30 days**
* **31–90 days**
* **91–180 days**
* **180+ days**

The analysis examines whether bookings made further in advance are associated with higher cancellation risk.

### Key Observation

The analysis indicates an association between **longer lead times and higher cancellation risk**.

From a business perspective, long-lead bookings deserve particular attention because they represent a higher cancellation-risk segment.

## However, the analysis identifies an **association rather than proving that longer lead time directly causes cancellations**.


## 4. Cancellation Rate by Deposit Type

Deposit type produced one of the strongest differences in the analysis:

| Deposit Type | Bookings | Cancelled | Cancellation Rate |
| ------------ | -------: | --------: | ----------------: |
| Refundable   |      162 |        36 |        **22.22%** |
| No Deposit   |  104,163 |    29,637 |        **28.45%** |
| Non Refund   |   14,572 |    14,479 |        **99.36%** |

### Key Observation

**Non Refund bookings have an exceptionally high cancellation rate of 99.36%.**

However, the very high rate required further investigation rather than immediately assuming that the deposit policy itself causes cancellations.


---

# 🔎 Investigating the Non Refund Cancellation Rate

Because the Non Refund category showed an unusual cancellation rate, the analysis went deeper instead of treating the result as a final conclusion.

The investigation examined:

1. Sample size
2. Non Refund bookings directly
3. Cancellation rate by hotel type
4. Cancellation rate by market segment
5. Cancellation rate by distribution channel

This is an important analytical step because an unusually high percentage should be investigated before drawing a business conclusion.


### Non Refund Sample Size

There are **14,572 Non Refund bookings**, of which **14,479 were cancelled** and only **93 were not cancelled**.

### Market Segment Investigation

Within the Non Refund subset, the notebook shows extremely high cancellation rates across the examined market segments:

| Market Segment | Bookings | Cancelled | Cancellation Rate |
| -------------- | -------: | --------: | ----------------: |
| Offline TA/TO  |    4,991 |     4,988 |        **99.94%** |
| Groups         |    9,172 |     9,110 |        **99.32%** |
| Online TA      |       56 |        53 |        **94.64%** |
| Corporate      |      334 |       312 |        **93.41%** |
| Direct         |       19 |        16 |        **84.21%** |

### Analytical Interpretation

The Non Refund result should therefore be treated as an **investigation finding**, not simply as evidence that non-refundable policies cause cancellations.

The pattern suggests that the Non Refund category is associated with a very unusual booking profile, and additional business context would be required to understand why these bookings are recorded as cancelled.

---
## 5. Cancellation Rate by Distribution Channel

The analysis also examines booking outcomes across distribution channels.

This helps identify whether cancellation behavior differs depending on how reservations enter the hotel booking system.

### Analytical Focus

The distribution-channel analysis compares:

* Direct
* Corporate
* TA/TO
* GDS
* Undefined

The analysis uses cancellation rate rather than simply comparing the number of cancellations, allowing channels with different booking volumes to be compared more fairly.

---


## 6. Overall Cancellation Rate by Market Segment

The project also examines cancellation rates across market segments.

The purpose is to understand whether different customer acquisition or booking segments exhibit different cancellation behavior.

This analysis provides another dimension for identifying potentially higher-risk booking groups and complements the distribution-channel analysis.

---

# 💡 Business Insights

Based on the exploratory analysis, several patterns stand out:

### 1. Cancellation is a significant operational issue

With an overall cancellation rate of **37.13%**, more than one in three bookings in the final dataset were cancelled.

### 2. City Hotels show higher cancellation risk

City Hotel bookings have a cancellation rate of **41.71%**, compared with **27.98%** for Resort Hotels.

### 3. Longer lead times are associated with higher cancellation risk

Bookings made further in advance appear to carry greater cancellation risk, making long-lead reservations a useful segment for monitoring.

### 4. Deposit type shows an exceptionally strong relationship with cancellation

The **99.36% cancellation rate for Non Refund bookings** is the most unusual pattern identified in the project.

### 5. Unusual patterns require investigation

Rather than assuming that a single variable explains cancellation behavior, the analysis investigates the Non Refund segment across additional dimensions such as hotel type, market segment, and distribution channel.
