# DATA MODELLING WITH APACHE CASSANDRA

This documentation outlines a data engineering project that demonstrates relational data modeling using Apache Cassandra, a NoSQL database. It extracts data from CSV files, creates and populates tables in Cassandra, and executes three specific queries to retrieve data.

## Table of Contents

- [Introduction](#introduction)
- [Importing Python Packages](#importing-python-packages)
- [Extracting Data from CSV Files](#extracting-data-from-csv-files)
- [Loading Data into a Single CSV File](#loading-data-into-a-single-csv-file)
- [Apache Cassandra Provisioning and Set-Up](#apache-cassandra-provisioning-and-set-up)
- [Cassandra DB Query Set-Up](#cassandra-db-query-set-up)
- [Creating Cassandra Tables](#creating-cassandra-tables)
- [Inserting Data into Cassandra Tables](#inserting-data-into-cassandra-tables)
- [Verifying Data in Cassandra Tables](#verifying-data-in-cassandra-tables)
- [Dropping Tables and Closing Session](#dropping-tables-and-closing-session)
- [License](#license)

## Introduction

This README provides an overview of the ETL (Extract, Transform, Load) process implemented in the Python script. The script's purpose is to extract data from CSV files, transform it into a structured format, and load it into Apache Cassandra tables. Below, we detail each step of the process.

## Importing Python Packages:

At the beginning of the script, essential Python packages are imported to facilitate data processing:

- Pandas: Used for data manipulation.
- Cassandra: Used for database interaction.
- Other standard libraries for file and data handling.

## Extracting Data from CSV Files:

The script follows these steps to extract data from CSV files located in a directory named "event_data":

1. It uses the `os` and `glob` libraries to obtain a list of file paths to process all CSV files in the specified directory.

2. The script reads each CSV file, skipping the header row, and extracts data row by row.

3. Extracted data is collected into a list called `full_data_rows_list`, which will be used for further processing and loading into the Cassandra database.

4. The script prints the total number of rows extracted from all files.

## Loading Data into a Single CSV File:

To organize the extracted data into a structured format, it is loaded into a single CSV file named "event_data.csv" with these steps:

1. It creates a CSV writer object and specifies the columns to be included in the new CSV file.

2. The script iterates through the extracted data, filters out empty rows, and writes the selected columns to the new CSV file.

3. The final count of rows in the new CSV file is printed.

## Apache Cassandra Provisioning and Set-Up:

The script sets up a connection to an Apache Cassandra database:

1. It uses the Cluster and Session classes from the Cassandra driver to create a connection to the Cassandra cluster running on localhost.

2. The script specifies the keyspace (similar to a database in Cassandra) to use for further queries.

## Cassandra DB Query Set-Up:

Queries for specific data analysis are defined as follows:

1. Three Cassandra queries are defined to answer specific questions (queries) about the data.

## Creating Cassandra Tables:

For each query, the script creates a corresponding Cassandra table:

1. The table schema includes column names and data types.

2. The primary key and clustering columns are defined to optimize query performance.

## Inserting Data into Cassandra Tables:

The script reads the extracted data again and inserts it into the appropriate Cassandra table:

1. It constructs and executes INSERT queries for each row of data, mapping CSV columns to table columns.

## Verifying Data in Cassandra Tables:

To ensure the data has been successfully inserted into the Cassandra tables, the script executes SELECT queries:

1. It converts the query results into Pandas DataFrames for easier inspection.

## Dropping Tables and Closing Session:

Once the data has been verified, the script includes a section for dropping the Cassandra tables and closing the Cassandra session to clean up resources.

Feel free to modify and expand this README section as needed to provide additional context or instructions for using your ETL script.

## License

The Jupyter Notebook is licensed under the MIT License.
