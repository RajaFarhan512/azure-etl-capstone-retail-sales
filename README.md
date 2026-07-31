# azure-etl-capstone-retail-sales
End-to-end Azure ETL pipeline project using Azure Data Factory, Blob Storage, and Power BI.
# Azure End-to-End ETL Capstone Project – Retail Sales Analytics

## Project Overview

This project demonstrates an end-to-end ETL (Extract, Transform, Load) pipeline using Microsoft Azure. The solution ingests a public retail sales dataset into Azure Blob Storage, transforms the data using Azure Data Factory Mapping Data Flow, stores the cleaned data in a curated layer, and visualizes business insights in Power BI.

## Project Architecture

```
Kaggle Retail Sales Dataset
        ↓
Azure Blob Storage (Raw)
        ↓
Azure Data Factory Pipeline (pl_ingest_curate)
        ↓
Mapping Data Flow
        ↓
Azure Blob Storage (Curated)
        ↓
Power BI Dashboard
```

## Dataset Information

* **Source:** Kaggle Retail Sales Dataset
* **File Format:** CSV
* **Dataset Size:** Under 100 MB
* **Key Fields:**

  * Transaction ID
  * Date
  * Customer ID
  * Gender
  * Age
  * Product Category
  * Quantity
  * Price per Unit
  * Total Amount

## Business Question

How can retail sales data be transformed and analyzed to identify sales trends, customer demographics, and product category performance?

## Azure Resources Used

* Azure Resource Group
* Azure Storage Account
* Azure Blob Storage

  * Raw Container
  * Curated Container
* Azure Data Factory
* Mapping Data Flow
* Power BI Desktop

## ETL Process

### Extract

* Downloaded the Retail Sales dataset from Kaggle.
* Uploaded the original CSV file to the **raw** Blob Storage container.

### Transform

The Mapping Data Flow performed the following transformations:

* Removed records with missing Transaction ID values.
* Added a new derived column named **Sales_Category** to classify transactions as High Value or Regular.

### Load

* Loaded the transformed dataset into the **curated** Blob Storage container.
* Verified the pipeline completed successfully using Azure Data Factory Monitor.

## Power BI Dashboard

The dashboard includes:

* Total Sales KPI Card
* Sales by Product Category
* Monthly Sales Trend
* Sales by Gender
* Transaction Details Table

These visuals provide insights into revenue, product performance, customer demographics, and sales trends.

## Monitoring and Validation

The Azure Data Factory Monitor was used to verify that the pipeline completed successfully. The curated dataset was checked to confirm that the transformations were applied correctly.

## Cost Optimization

To minimize Azure costs:

* Used an Azure for Students subscription.
* Used a dataset smaller than 100 MB.
* Limited pipeline executions during development.
* Avoided expensive Azure services.
* Deleted unnecessary resources after completing the project.

## Repository Contents

```
data/
    raw/
    curated/

dashboards/

screenshots/

README.md
```

## Conclusion

This project successfully demonstrates a complete cloud-based ETL pipeline using Microsoft Azure. Data was ingested, transformed, validated, and visualized to produce meaningful business insights while following cost-effective cloud practices.
