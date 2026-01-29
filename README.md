# 🛒 Real-Time E-Commerce Data Pipeline

An end-to-end streaming data engineering project that processes real-time e-commerce transactions using **Azure Event Hubs**, **Azure Databricks**, and **Delta Lake**. This pipeline follows the **Medallion Architecture** (Bronze, Silver, Gold) to ingest, clean, and aggregate data for downstream analytics.

## 🚀 Project Overview
This project simulates a live e-commerce environment where order data is generated continuously. The data flows through a pipeline designed for low-latency processing and fault tolerance.

* **Ingestion:** Python script generates mock order data and pushes it to Azure Event Hubs.
* **Processing:** Databricks (Apache Spark) reads the stream using the Kafka protocol.
* **Storage:** Data is stored in Azure Data Lake Storage (ADLS) Gen2 using **Delta Lake** format.
* **Transformation:** * **Bronze:** Raw data ingestion (Append-only).
    * **Silver:** Cleaned data with correct types and deduplication.
    * **Gold:** Aggregated business metrics (Revenue per City/5-min windows).

## 🏗️ Architecture
**Data Flow:**
`[Python Data Generator]` → `[Azure Event Hubs]` → `[Databricks (Spark Structured Streaming)]` → `[ADLS Gen2 (Delta Lake)]`

1.  **Source:** `generate_order.py` (Simulates User Orders)
2.  **Message Broker:** Azure Event Hubs (Kafka Interface)
3.  **Bronze Layer:** Raw JSON ingestion to Delta Table.
4.  **Silver Layer:** Schema enforcement, Timestamp conversion, Watermarking for late data.
5.  **Gold Layer:** Windowed Aggregation (Total Sales & Order Count per City).

## 🛠️ Tech Stack
* **Cloud:** Microsoft Azure
* **Streaming:** Azure Event Hubs
* **Compute:** Azure Databricks (Apache Spark 3.x)
* **Storage:** Azure Data Lake Storage (ADLS) Gen2
* **Format:** Delta Lake
* **Language:** Python (PySpark)
* **Development:** VS Code (Local), Databricks Notebooks

## 📂 Repository Structure
