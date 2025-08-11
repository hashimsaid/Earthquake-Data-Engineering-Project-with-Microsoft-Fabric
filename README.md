# Earthquake Data Engineering Project on Microsoft Fabric

## Overview

This project demonstrates an end-to-end data engineering pipeline built using **Microsoft Fabric** and the **Medallion Architecture**. The goal is to ingest, transform, and analyze earthquake event data from the **USGS Earthquake Hazards Program API**.

The pipeline is structured into three layers, each represented by a Synapse notebook:

-   **Bronze Layer**: Raw data ingestion. This notebook uses Python's `requests` library to fetch raw GeoJSON data from the USGS API and saves it in a raw state within the Fabric Lakehouse.
-   **Silver Layer**: Data cleansing and transformation. This notebook uses **PySpark** to read the raw JSON files, flatten the nested data structure, and perform basic data type conversions. The result is a clean, structured table.
-   **Gold Layer**: Business-ready data. This notebook applies business logic to the silver data, adding new columns like a significance classification and a country code using a User-Defined Function (UDF). The final table is ready for reporting and analytics.

The entire workflow is designed to be orchestrated by **Data Factory** 

Earthquake API: https://earthquake.usgs.gov/fdsnws/ev...
## Technologies Used

-   **Microsoft Fabric**: The unified platform for all data services.
-   **Synapse Data Engineering**: Used for running the PySpark notebooks.
-   **Python & PySpark**: The primary languages for data ingestion and transformation.
-   **USGS API**: The external data source for earthquake events.
