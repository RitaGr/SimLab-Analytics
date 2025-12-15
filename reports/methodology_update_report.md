# Methodology Update Report

**Project:** Boutique Retail Analytics in a Simulated Environment
**Platform:** Bookstore Simulation
**Author:** Founder & Data Analyst
**Date:** 15.12.2025

---

## 1. Purpose of This Report

This report documents key methodological findings identified during the data collection test and the resulting design decisions made to align the analytical model with the constraints of the simulation environment.

The objective is to ensure that the project remains:

* methodologically sound
* transparent about limitations
* aligned with real-world analytical practices

---

## 2. Initial Assumptions

At the outset of the project, the analytical design assumed:

* Item-level visibility of inventory (individual book titles)
* Persistent identifiers for books across customers and sessions
* The ability to construct a book catalogue as a core entity
* Customer-level tracking similar to traditional retail analytics

These assumptions informed the first draft of the data dictionary and collection protocol.

---

## 3. Key Findings During Initial Observation

### 3.1 Inventory and Transaction Granularity

During the first structured data collection session, it became clear that:

* The simulation does **not expose persistent book titles** as inventory units.
* Book titles appear only transiently during recommendation interactions.
* Titles cannot be reliably tracked across customers, transactions, or sessions.
* Observable purchase behavior is consistently available **only at the genre level**.

**Conclusion:**
Item-level analysis is not supported by the system and cannot be performed reliably.

---

### 3.2 Customer Identifiability

Additional observations revealed that:

* Not all customers appear as discrete characters.
* There is no mechanism to identify returning customers across sessions, except registered returning customers.
* Persistent customer identifiers cannot be assigned without inference.

**Conclusion:**
Customer-level tracking must be treated as **anonymous and session-bound**, reflecting per-visit observation rather than persistent identity. Only the registered returning customers will have their unique identifiers. 

---

## 4. Methodological Implications

These findings necessitated a revision of the analytical design:

* Item-level entities (books, catalogue entries) cannot be justified.
* Persistent customer identifiers would imply tracking capabilities not present in the system.
* Analytical scope must shift from item-based optimization to **category-level behavior analysis**.

---

## 5. Design Decisions

### 5.1 Removal of Book Catalogue

**Decision:**
The book catalogue entity was removed entirely from the data model.

**Rationale:**
Maintaining a catalogue would imply control, visibility, and persistence of item-level data that is not observable in the simulation. Generating synthetic titles was explicitly rejected to avoid introducing fictional precision.

---

### 5.2 Adoption of Genre-Level Modeling

**Decision:**
Genre was adopted as the primary analytical unit for inventory, transactions, and customer preference.

**Rationale:**
Genre represents the highest stable and observable level of granularity consistently available in the system. In this environment, genre functions as the effective “SKU*” (Stock Keeping Unit).

*An SKU is the smallest distinct unit of a product that a business tracks

---

### 5.3 Anonymous, Session-Level Customer Representation

**Decision:**
Customers are modeled as anonymous visits with session-scoped identifiers only, except registered returning customers.

**Rationale:**
This reflects both simulation constraints and real-world retail practices where many customers remain untracked due to privacy, lack of loyalty systems, or regulatory limits.

---

## 6. Revised Analytical Scope

### Enabled Analyses

* Genre-level conversion rates
* Customer preference vs. purchase alignment
* Engagement differences across genres
* Impact of recommendations on conversion
* Comparison between niche and mainstream genres

### Explicitly Out of Scope

* Title-level performance analysis
* SKU-specific pricing elasticity
* Long-tail item optimization
* Returning-customer lifetime analysis

These exclusions are documented intentionally to preserve analytical integrity.

---

## 7. Ethical and Professional Considerations

The decision not to invent identifiers or simulate unavailable data reflects a commitment to:

* transparency
* methodological honesty
* privacy-aware modeling

This approach aligns with professional standards in data analytics, where analysts are expected to adapt to data limitations rather than obscure them.

---

### End of Document

---