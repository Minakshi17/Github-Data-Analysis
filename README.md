# Analysed Github 17th July Data
ETL pipeline

Extracted data from GHarchive ------> Transformed the data in PySpark -------> Load the target data in AWS-S3 bucket for day-to-day pipeline

Followed the following steps to get the analysis done:

## Extracting data files from GHarchive
## Processing the Data
## Understanding the data
## Analysing the data with a problem statement
## Data Visualisation
## Exported dataframe with relevant fields into S3 bucket(where business can create a trigger using AWS lambda) for day-to-day pipeline analysis

# Extracted data files from GHArchive

  Used wget command to download the data for a day
  The data was a compressed .gz file for each hour
  I initially decompressed the data in my system, however the data size was more than 23GB and therefore, I decided to work on the compressed file online and decided on using      online Databricks to understand and manipulate the data

# Processed the Data
  Created a Spark.Session and I read all the json data in one single data frame
  Used to_timestamp function to change string data to datetime column and further user hour fuction to extract hourly value
  Created in memory table and then Cached my table for faster code execution

# Understood the Data
  Used PrintSchema to see nested structure of DataFrame
  On further investigation observed that payload column has most information

# Analysed Data
Formulated Question which can be helpful to get major insight from data
  What are the different type of events that took place in a day?
  How many issues were raised per hour in a day?
  How many issues were opened and closed per hour in a day?


