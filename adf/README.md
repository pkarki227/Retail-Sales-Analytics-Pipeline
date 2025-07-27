# Azure Data Factory Pipeline

This folder contains the ARM template JSON export of the Azure Data Factory pipeline used in this project.

- **Pipeline**: CopyGitHubToADLS
- **Description**: Copies retail sales CSV data from GitHub HTTP source to Azure Data Lake Storage Gen2 raw container.
- **Datasets**: 
  - GitHubRetailSalesDataset (HTTP source)
  - ADLSGen2RawDataset (ADLS Gen2 sink)

You can deploy this pipeline ARM template in your Azure subscription to replicate the ingestion pipeline.
