## Databricks Notebooks

- **Data_Transformation_Raw_to_Processed.py**  
  Cleans the raw retail sales data by parsing dates, casting data types, removing duplicates,  
  adding a `TotalRevenue` column, and saving the cleaned CSV file to the processed ADLS Gen2 container.

- **managed_table_metastore.py**  
  Loads the cleaned CSV file from the processed container and saves it as a managed Delta table  
  (`retail_analytics.retail_sales_cleaned`) in the Databricks metastore for downstream querying.
