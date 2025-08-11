# Earthquake Data Engineering Project on Microsoft Fabric

## Overview

This project demonstrates an end-to-end data engineering pipeline built using **Microsoft Fabric** and the **Medallion Architecture**. The goal is to ingest, transform, and analyze earthquake event data from the **USGS Earthquake Hazards Program API**.

The pipeline is structured into three layers, each represented by a Synapse notebook:

-   **Bronze Layer**: Raw data ingestion. This notebook uses Python's `requests` library to fetch raw GeoJSON data from the USGS API and saves it in a raw state within the Fabric Lakehouse.
-   **Silver Layer**: Data cleansing and transformation. This notebook uses **PySpark** to read the raw JSON files, flatten the nested data structure, and perform basic data type conversions. The result is a clean, structured table.
-   **Gold Layer**: Business-ready data. This notebook applies business logic to the silver data, adding new columns like a significance classification and a country code using a User-Defined Function (UDF). The final table is ready for reporting and analytics.

The entire workflow is designed to be orchestrated by **Data Factory** and visualized in a **Power BI** dashboard.

## Technologies Used

-   **Microsoft Fabric**: The unified platform for all data services.
-   **Synapse Data Engineering**: Used for running the PySpark notebooks.
-   **Python & PySpark**: The primary languages for data ingestion and transformation.
-   **USGS API**: The external data source for earthquake events.
-   **Power BI**: For data visualization and reporting.

## How to Run This Project

1.  **Clone the Repository**: Clone this GitHub repository to your local machine.
2.  **Import Notebooks**: Import the three notebooks (`bronze_notebook.ipynb`, `silver_notebook.ipynb`, `gold_notebook.ipynb`) into your Microsoft Fabric workspace.
3.  **Configure Data Factory**: Set up a Data Factory pipeline to orchestrate the execution of the notebooks in the correct order (Bronze -> Silver -> Gold), passing the `start_date` and `end_date` parameters.
4.  **Connect Power BI**: Create a Power BI report connected to the `earthquake_events_gold` table in your Lakehouse to visualize the final data.

Feel free to explore the code, provide feedback, or suggest improvements!
