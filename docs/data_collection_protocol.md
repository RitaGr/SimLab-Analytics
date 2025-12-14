# Data Collection Protocol v1

**Project:** Boutique Retail Analytics in a Simulated Bookshop

---

## 1. Purpose

This protocol defines how customer and transaction data are collected from a  
simulated boutique bookshop environment.

The objective is to ensure data is collected consistently across sessions,  
with clearly defined observation units, variables, and limitations.

---

## 2. Observation Environment

- **Environment Type:** Simulated retail environment
- **Observation Method:** Structured manual observation
- **Session Duration:** 20–30 minutes per session
- **Data Capture:** Manual logging into structured tables
    
No automated data extraction tools are used at this stage.

---

## 3. Observation Units

### 3.1 Customer Visit (Primary Unit)

A _customer visit_ begins when a customer enters the bookshop and ends when  
the customer exits the shop, regardless of whether a purchase is made.

Each customer visit is recorded as a single observation.

---

### 3.2 Transaction (Secondary Unit)

A _transaction_ is recorded when a customer completes a purchase.

A single customer visit may result in:

- zero transactions, or
- one transaction containing one or more items.
    
---

## 4. Recorded Entities and Variables

### 4.1 Customer Table (`customers.csv`)

|Variable|Description|
|---|---|
|customer_id|Unique identifier assigned by observer|
|session_id|Identifier for observation session|
|arrival_minute|Minute of session when customer enters|
|expressed_preference|Observed genre or interest|
|engagement_level|Low / Medium / High|
|purchased|0 = no purchase, 1 = purchase|
|notes|Optional qualitative notes|

---

### 4.2 Transaction Table (`transactions.csv`)

|Variable|Description|
|---|---|
|transaction_id|Unique transaction identifier|
|customer_id|Links to customer table|
|book_id|Identifier of purchased book|
|genre|Genre of purchased book|
|price|Sale price|
|timestamp_minute|Minute of session when purchase occurs|

---

## 5. Coding Guidelines

### 5.1 Engagement Level

- **Low:** Brief browsing, minimal interaction, early exit
- **Medium:** Browses multiple shelves, moderate time spent
- **High:** Extended browsing, multiple interactions, clear intent

Engagement level is assessed once per customer visit.

---

### 5.2 Expressed Preference

Preferences are recorded only when visibly indicated through browsing behavior  
(e.g., repeated interaction with a genre or section).

If no clear preference is observed, the value is recorded as `Unknown`.

---

## 6. Session Metadata

For each session, the following metadata is recorded separately:

- Session date
- Session ID
- Notable environmental factors (events, layout changes)

---

## 7. Data Quality and Limitations

- All observations are subject to observer interpretation.
- Engagement and preference variables are qualitative and discretized.
- Data volume is expected to be limited and non-representative.

These limitations are acknowledged and documented to avoid overinterpretation.

---

## 8. Revision Policy

This protocol may be updated as observation challenges or ambiguities are  
identified. All revisions will be documented with version numbers and dates.

---

## 9. Status

Protocol version 1.0 — Initial draft. Data collection has not yet begun.

---

### End of Document

---
