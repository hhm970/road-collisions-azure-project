# Azure Road Collisions Project

## Description

**See `Project_Brief.md`**

## Data Sources

- Road collision data for the last 5 years: https://data.dft.gov.uk/road-accidents-safety-data/dft-road-casualty-statistics-collision-adjustment-last-5-years.csv (downloadable manually from https://data.gov.uk/dataset/road-accidents-safety-data)
- UK postcode data: https://www.arcgis.com/sharing/rest/content/items/f7464f3658ba439ba577651b32014cfe/data (downloadable manually from https://geoportal.statistics.gov.uk/datasets/ons::national-statistics-postcode-lookup-2021-census-may-2024-for-the-uk/about)

## Requirements

### Pre-requisites

In your Azure environment, ensure each of these services are set up:

- Azure Databricks Service: in a workspace titled `sl-dbw-spark-uks-01`, ensure the workspace is set up. More info on setting up Spark clusters can be found in `databricks_notebook/README.md`.
- Azure Blob Storage: in a storage account titled `slstasparkuks01`, ensure that a Blob container titled `raw-data` is set up to store the raw road collision data.
- Azure Data Lake Storage: in a storage account titled `sldlssparkuks01`, ensure that 4 containers are set up,
    - `raw-data`: Used to store the raw contents of UK postcode data;
    - `raw-data-modified`: These should contain 2 directories:
        - `howard/collision`: Used to contain road collision data (result of filtering rows from raw collision data; due to be added into ADF pipeline!);
        - `howard/postcode`: Used to contain a singular postcode CSV file, as a result of merging multiple postcode CSV files;
    - `cleaned-data-sql-tables`: Used to contain CSV files, which are written into PostgreSQL tables;
    - `cleaned-data-parquet`: Used to contain clean data in Parquet format.
- Azure Key Vault: Used to contain account keys and SAS tokens for accessing storage services, as well as the password to the PostgreSQL database instance. Note that each individual Blob container will require a credential.
- Azure PostgreSQL Database: ensure that an instance titled `sl-psql-spark-uks-01` has a database titled `uk_road_safety`.
- Azure Data Factory: ensure that an instance titled `sl-adf-spark-uks-01` has the following set up,
    - Pipeline: Ensure that a pipeline is created titled `sl-spark-howard-road-safety-pipeline`. Copy the data from `az-data-factory/pipeline.json` into the JSON representation interface.
    - Linked services: Ensure that linked services are made to correspond to each of the above Azure tools, respectively titled `AzureBlobStorage`, `AzureDatabricksCommon`, `AzureDataLakeStorage`, `AzurePostgreSQL`.
    - Datasets: Ensure that datasets are made for each file in `az-data-factory/datasets`.
    - More info about replicating the architecture as Infrastructure as Code via Terraform can be found in the `az-data-factory` directory.

Additionally, ensure the user has each of these roles:
- Reader
- Data Factory Contributor
- Storage Blob Data Contributor

## Cloud Deployment

## Folder Structure Explained