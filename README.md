## Project: Data Lake

### Overview

This project contains a script and configuration file to create a set of Spark 
DataFrames for the purposes of data analysis. The source of the tables are json files 
located in s3. Once the tables have been populated, they are persisted to partitioned
parquet files in s3.

The background for the project is described [here](https://github.com/Raphael-C98/Project-Data-Modeling-with-Postgres#readme).

### Details

Project files:

etl.py is a pyspark script that copies data from json files in S3 into staging tables, then loads it 
into the final destination tables.

dl.cfg is a configuration file that contains environment-specific settings.

### How to run

#### Prerequisites 

The AWS password and secret must be defined in your environment before running 
`etl.py`:

```commandline
export KEY=<key>
export SECRET=<secret>
```

#### Run mode

Run etl.py to read from the song and logs json files, denormalize the data into fact and dimension tables and gives the output of these tables in S3 in the form of parquet files.
