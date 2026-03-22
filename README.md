# Apple Global Sales Analysis — MDA2 Group Assignment

**Modern Data Architectures for Big Data II | IE University MBDS 2026 | Section 1, Group 5**

## Overview

This project delivers an end-to-end big data analysis of Apple's global sales performance (2022–2024), built on a medallion lakehouse architecture using PySpark, Apache NiFi, MinIO, and Spark MLlib. The goal is to surface actionable strategies for improving Apple's global revenue across products, channels, and markets.

## Business Questions

1. Which Apple products should be prioritised to drive revenue?
2. What sales channel strategy is most effective across different markets?
3. Which markets present greater growth opportunities for Apple?

## Repository Contents

| File | Description |
|------|-------------|
| `Apple_analysis_worldpopulation-_Notebook.ipynb` | Full PySpark analysis notebook — EDA, GraphFrames market similarity, MLlib ML pipeline (Linear Regression + Random Forest), and business insights |
| `NIFI_set_up_two.json` | Apache NiFi 2.0 flow definition for automated data ingestion (Kaggle + IMF CPI API → MinIO) |
| `MDA2_Group_Presentation.pptx` | Final business presentation deck |

## Tech Stack

- **Compute**: PySpark (Spark MLlib, GraphFrames, Spark Structured Streaming)
- **Storage**: MinIO (S3-compatible object store) — Bronze / Silver / Gold medallion architecture
- **Ingestion**: Apache NiFi 2.0
- **ML**: Linear Regression, Random Forest (with VIF checks, log transformation, LOO cross-validation)
- **Graph Analytics**: GraphFrames — market similarity network

## Data Sources

- [Apple Global Product Sales 2022–2024](https://www.kaggle.com/datasets/ashyou09/apple-global-product-sales-dataset) — Kaggle
- [World Population Data 2025](https://github.com/sharmadhiraj/free-json-datasets) — GitHub open dataset
- IMF CPI API — macroeconomic context for inflation-adjusted analysis

## Setup

### Prerequisites

- Apache Spark 3.4+ with PySpark
- Apache NiFi 2.0
- MinIO (local or cloud)
- Python 3.9+

### NiFi Flow

Import `NIFI_set_up_two.json` directly into NiFi's Process Group via **Upload Template** (NiFi 2.0: drag-and-drop JSON into the canvas). Configure your MinIO credentials and Kaggle API key in the Controller Services before starting the flow.

### Notebook

Run `Apple_analysis_worldpopulation-_Notebook.ipynb` in a Jupyter environment with a PySpark kernel. Ensure MinIO is running and the Bronze layer has been populated by the NiFi flow before executing the Silver/Gold transformation cells.

## Architecture

```
Data Sources (Kaggle, IMF API)
        │
   Apache NiFi 2.0
        │
   MinIO (Bronze)
        │
  PySpark ETL
   ├── Silver (cleaned, enriched)
   └── Gold (aggregated, ML-ready)
        │
  Spark MLlib + GraphFrames
        │
  Business Insights & Presentation
```

---

*IE University — Master in Business Analytics & Data Science 2026*
