# Project Brief: Building an ETL Pipeline with UK Road Safety Data

## Phase 1: Dataset Exploration and Transformation in Databricks

**Objective**: In the first phase, you will focus on cleaning and transforming the UK Road Safety dataset using PySpark on Databricks. This will provide a strong foundation in working with large datasets and distributed computing using PySpark.

### **Tasks**:

1. **Dataset Loading**:
   - Load the UK Road Safety dataset into a Databricks notebook.
   - Review the structure and column types to ensure data is in a format suitable for analysis.

2. **Data Cleaning**:
   - Identify rows with missing or invalid data (e.g., missing accident severity, latitude, longitude).
   - Remove invalid rows and ensure the remaining data is complete and usable.
   - Ensure geolocation data (longitude and latitude) is valid and falls within realistic ranges for the UK.

3. **Data Transformation**:
   - **Create new columns**:
     - Extract `Accident Year`, `Accident Month`, and `Accident Hour` from the date and time columns.
   - **Feature engineering**:
     - Enrich the dataset by adding relevant columns from an external dataset (such as mapping accidents to regions using a postcode lookup).
     - You’ll need to identify how to map accidents to regions based on coordinates.

4. **Data Aggregation and Basic Analysis**:
   - Aggregate the dataset to find high-risk locations based on accident severity and frequency.
   - Analyze accident patterns (e.g., by time of day or month) using basic aggregations.

5. **Notebook Deliverable**:
   - By the end of Phase 1, you should have a Databricks notebook that:
     - Loads the dataset.
     - Cleans and transforms the data.
     - Performs basic aggregations and analysis to identify trends in the data.

### **Resources**:
- UK Road Safety Data: [https://data.gov.uk/dataset/road-accidents-safety-data](https://data.gov.uk/dataset/road-accidents-safety-data)
- UK Postcode Lookup Dataset: [https://geoportal.statistics.gov.uk/datasets/73ce619853044aaaa6f7fa5b90765b85/about](https://geoportal.statistics.gov.uk/datasets/73ce619853044aaaa6f7fa5b90765b85/about)

---

## Phase 2: Full Integration with Azure Ecosystem

**Objective**: In Phase 2, you will integrate your PySpark pipeline into the broader Azure ecosystem. This includes ingesting data into Azure Data Lake Storage (ADLS), transforming it in Databricks, and storing final results in Azure SQL Database. You will also automate the pipeline using Azure Data Factory (optional).

### **Tasks**:

1. **Ingest Data into Azure Data Lake Storage (ADLS)**:
   - Upload the raw UK Road Safety data to an Azure Data Lake container.
   - Modify your PySpark code to read from ADLS instead of local storage.

2. **Data Transformation and Aggregation in Databricks**:
   - Use the PySpark code you developed in Phase 1 to perform transformations on data stored in ADLS.

3. **Store Processed Data in ADLS**:
   - Save the cleaned and transformed data back to ADLS in Parquet format.

4. **Store Aggregated Results in Azure SQL Database**:
   - Write the results of your analysis (e.g., high-risk accident locations) to an Azure SQL Database for querying and reporting.

5. **(Optional) Automate the Pipeline with Azure Data Factory**:
   - Set up Azure Data Factory to trigger the Databricks notebook and automate the data ingestion, transformation, and loading process.

---

## **Timeline**

- **Phase 1**: Focus on PySpark transformations in Databricks. Deliver the cleaned and transformed dataset notebook by the end of **Week 1**.
- **Phase 2**: Integrate the pipeline into Azure services and deliver the final solution by the end of **Week 2**.

### **Phase 1 Deliverables**:

A Databricks notebook that demonstrates:

1. Data loading and cleaning (e.g., removing missing or invalid data).
2. Data transformations (e.g., feature extraction, mapping to regions).
3. Basic aggregation and analysis (e.g., identifying high-risk accident locations).

### **Phase 2 Deliverables**:

Fully integrated PySpark pipeline with Azure services, including:

1. Data ingestion from Azure Data Lake.
2. Transformation and analysis in Databricks.
3. Processed data stored in ADLS.
4. Aggregated results stored in Azure SQL Database.
5. (Optional) Automated pipeline using Azure Data Factory.