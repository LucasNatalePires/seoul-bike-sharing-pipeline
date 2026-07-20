# Seoul Bike Sharing — Big Data Analytics Pipeline

Academic project for the **Big Data and Data Analytics** module — CCT College Dublin (Higher Diploma, L7).

End-to-end big data pipeline built around the [Seoul Bike Sharing Demand](https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand) dataset, covering distributed batch processing, NoSQL querying, and real-time streaming.

## Overview

The project answers three questions using a stack of distributed technologies:

| # | Question | Tech stack | Notebook |
|---|----------|-----------|----------|
| 1 | Batch EDA & querying of historical bike rental data | HDFS, PySpark | [`notebooks/CA2_SBA25076.ipynb`](notebooks/CA2_SBA25076.ipynb) |
| 2 | Document-store querying for demand patterns | MongoDB | [`notebooks/CA2_SBA25076.ipynb`](notebooks/CA2_SBA25076.ipynb) |
| 3 | Real-time weather ingestion & pattern detection | Spark Structured Streaming, Open-Meteo API | [`notebooks/Q3_-_SBA25076.ipynb`](https://github.com/LucasNatalePires/seoul-bike-sharing-pipeline/blob/main/notebooks/Q3%20-%20SBA25076.ipynb) |

## Pipeline summary

**1. Batch processing (HDFS + PySpark)**
- Loaded the raw CSV from HDFS, fixed corrupted Unicode column headers and renamed columns
- Cleaned schema (date parsing, type checks), checked duplicates/nulls, ran descriptive statistics
- Queried seasonal record distribution, seasonal demand, and rental averages by temperature band

**2. NoSQL analysis (MongoDB)**
- Loaded the processed dataset into MongoDB
- Queried top demand hours (holiday vs. non-holiday), peak summer hours, and winter sub-zero rental behaviour

**3. Real-time streaming (Spark Structured Streaming)**
- Ingested live Seoul weather data from the Open-Meteo API
- Applied a defined schema, ran windowed aggregations, and detected two behavioural patterns (heat perception gap, wind alert flag)
- Compared batch vs. real-time processing trade-offs

## Repository structure

```
notebooks/
├── CA2_SBA25076.ipynb           # Q1 (HDFS/PySpark) + Q2 (MongoDB)
└── Q3_-_SBA25076.ipynb          # Q3 (Spark Streaming)
data/
├── SeoulBikeData.csv            # Historical batch dataset
└── weather_seoul_streaming.csv  # Captured streaming sample
docs/
└── Assignment_Brief.docx         # Original assessment brief
README.md
```

## Tech stack

`Hadoop HDFS` · `Apache Spark (PySpark)` · `Spark Structured Streaming` · `MongoDB` · `Open-Meteo API` · `Python`

## Data source

Seoul Bike Sharing Demand dataset — UCI Machine Learning Repository. Real-time weather data via the [Open-Meteo API](https://open-meteo.com/).

## Author

**Lucas** — Big Data and Data Analytics, CCT College Dublin
