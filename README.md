# Apple Global Sales Strategy & Data Architecture Analysis

**IE University — Master in Business Analytics & Data Science (2026)**
Modern Data Architectures for Big Data II | Section 1 — Group 5

---

## Overview

This project delivers an end-to-end analysis of Apple’s global sales performance (2022–2024), combining **modern data architecture** with **advanced analytics** to generate actionable business insights.

Built on a **medallion lakehouse architecture**, the project integrates data ingestion, distributed processing, and machine learning to identify the key drivers of revenue variation across global markets.

---

## Business Objective

Apple operates across 30+ markets with significant variation in revenue performance.

This project aims to answer:

* Which product categories drive the highest revenue?
* What sales channel strategies maximize performance?
* Which markets present the greatest growth opportunities?

---

## Key Insights

* **Product mix is the primary driver of revenue variation**
* **Premium devices significantly increase transaction value**
* **Direct Apple channels outperform third-party retail**
* **Large markets (India, China) remain underpenetrated**, representing major growth potential

---

## Architecture

```text
Data Sources (Kaggle, IMF API)
        │
   Apache NiFi (Ingestion)
        │
   MinIO (Bronze Layer)
        │
   PySpark ETL
   ├── Silver (cleaned, enriched)
   └── Gold (aggregated, ML-ready)
        │
   ML Models + Graph Analytics
        │
   Business Insights
```

---

## Tech Stack

* **Data Processing**: PySpark (Spark MLlib, Structured Streaming)
* **Data Ingestion**: Apache NiFi 2.0
* **Storage**: MinIO (S3-compatible, medallion architecture)
* **Machine Learning**: Linear Regression, Random Forest
* **Graph Analytics**: GraphFrames (market similarity network)

---

## Repository Structure

```text
├── notebook/
│   └── apple_sales_analysis.ipynb
├── pipeline/
│   └── nifi_pipeline.json
├── presentation/
│   └── project_presentation.pptx
├── data/
│   └── README.md  (datasets not included)
├── README.md
```

---

## Data Sources

Datasets are not included in this repository due to size and licensing considerations.

They can be accessed from public sources:

* Apple Global Product Sales Dataset (Kaggle)
* World Population Dataset (public JSON sources)

---

## How to Run

1. Download datasets from the sources above
2. Place them in a local `/data` folder
3. Configure MinIO and NiFi pipeline
4. Run the notebook in a PySpark environment

---

## Results & Impact

This project provides a data-driven framework for:

* **Market prioritisation**
* **Product strategy optimisation**
* **Channel strategy design**

It demonstrates how modern data architectures can be leveraged to support **strategic business decision-making at scale**.

---

## Author

Thomas Christian Matenco
MSc Business Analytics & Data Science
IE University
