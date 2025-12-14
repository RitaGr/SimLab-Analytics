# Data Dictionary

This document describes the structure, variables, and identifiers used
across all datasets in the project.

---

## ```customers.csv```

Each row represents a single customer visit.


| Column               | Type    | Description                            | Allowed Values           |
| -------------------- | ------- | -------------------------------------- | ------------------------ |
| customer_id          | string  | Unique identifier for customer visit   | C0001, C0002, …          |
| session_id           | string  | Observation session identifier         | S01, S02                 |
| arrival_minute       | integer | Minute of session when customer enters | ≥ 0                      |
| expressed_preference | string  | Observed genre interest                | Fantasy, Poetry, Unknown |
| engagement_level     | string  | Browsing intensity                     | Low, Medium, High        |
| purchased            | integer | Whether purchase occurred              | 0 or 1                   |
| notes                | string  | Optional qualitative notes             | Free text                |

---

## ```transactions.csv```

Each row represents a purchase event.


| Column           | Type    | Description                   | Allowed Values  |
| ---------------- | ------- | ----------------------------- | --------------- |
| transaction_id   | string  | Unique transaction identifier | T0001, T0002    |
| customer_id      | string  | Links to customers.csv        | C0001           |
| book_id          | string  | Purchased book identifier     | B001, B002      |
| genre            | string  | Genre of purchased book       | Fantasy, Poetry |
| price            | float   | Sale price                    | ≥ 0             |
| timestamp_minute | integer | Minute of session             | ≥ 0             |

---

## ```inventory_snapshots.csv```

Each row represents the stock level of a book at a specific snapshot time.


| Column        | Type    | Description         | Allowed Values |
| ------------- | ------- | ------------------- | -------------- |
| session_id    | string  | Observation session | S01            |
| snapshot_time | string  | Snapshot moment     | start, end     |
| book_id       | string  | Book identifier     | B001           |
| genre         | string  | Book genre          | Fantasy        |
| stock_level   | integer | Units available     | ≥ 0            |

---

##```book_catalog.csv```


| Column        | Type    | Description         | Allowed Values |
| ------------- | ------- | ------------------- | -------------- |
| book_id       | string  | Book identifier     | B00            |
| book_title    | string  | Book title          | Free text      |
| genre         | string  | Book genre          | Fantasy, Poetry|


---

## Identifier Conventions

- customer_id: C + zero-padded number (C0001)
- transaction_id: T + zero-padded number (T0001)
- session_id: S + two-digit number (S01)
- book_id: B + three-digit number (B001)

---

### End of Document

---