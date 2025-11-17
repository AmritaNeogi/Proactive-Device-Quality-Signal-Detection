# Proactive-Device-Quality-Signal-Detection
Proactive Device Quality Insight Pipeline



# ✅ **PIPELINE ORDER**

## **STEP 0 — Raw Data Source**

* Kaggle dataset (CSV) downloaded manually
  *(This is fine; many teams ingest CSV snapshots.)*

---

# **STEP 1 — SQL STAGE (Storage + Basic Cleaning)**

This simulates the “data engineering” part.
Here we do:

### ✔ Load raw CSV → SQL table (`reviews_raw`)

### ✔ Clean text + select required columns using SQL → (`reviews_clean`)

### ✔ (Optional) Convert dates, filter invalid rows

### ✔ (Optional) Enrich with sentiment or NLP output and store (`reviews_enriched`)

---

# **STEP 2 — NLP STAGE (Python)**

After SQL provides the clean table, Python reads from SQL and performs NLP.

### ✔ Text pre-processing

### ✔ Sentiment analysis (TextBlob/VADER)

### ✔ Keyword-based complaint features

### ✔ Optional ML complaint classifier

### ✔ Save back to SQL (`reviews_enriched`)

---

# **STEP 3 — Weekly Time-Series Aggregation (SQL or Python)**

Now we aggregate complaint signals into a structured time-series:

### ✔ Group by (device_brand, device_model, week)

### ✔ Compute total_reviews, total_complaints

### ✔ Compute complaint_rate


---

# **STEP 4 — Anomaly Detection & Quality Signal Generation (Python)**

Here is where your advanced work happens:

### ✔ Rolling mean & std

### ✔ Z-score anomalies

### ✔ Isolation Forest ML anomalies

### ✔ Strong signal flag (Z + IF)

### ✔ Export `quality_signals_tableau.csv`

---

# **STEP 5 — Tableau Dashboard**

Finally, visualize everything:

### ✔ Time series of complaint rate

### ✔ Highlight anomaly weeks

### ✔ Filters (brand/model/OS)

### ✔ Table of weekly strong signals

### ✔ Drill-down into complaint samples

---

# 🔥 **THE COMPLETE ORDER**

1. **SQL** — Raw storage → cleaning → enriched table
2. **NLP** — Sentiment + complaint extraction
3. **Aggregation** — Weekly device complaint stats
4. **Anomaly Detection** — Z-score + Isolation Forest
5. **Dashboard** — Tableau “Quality Signals”

---

