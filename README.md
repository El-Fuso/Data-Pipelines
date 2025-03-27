# Data-Pipelines

I built an ETL pipeline for Sparkify using Apache Airflow to automate and monitor data processing in their data warehouse.

The goal was to create dynamic, reusable data pipelines that support monitoring and easy backfills.

The pipeline consists of three main steps: staging data from S3, loading it into the data warehouse, and running data quality checks.

I used two datasets stored in S3: song data and log data, which are processed with AWS Redshift.

First, I staged the data into staging_events and staging_songs tables using a custom stage operator (stage_redshift.py).

Then, I loaded the transformed data into the fact table (songplays) using a fact operator (load_fact.py).

I also populated the dimension tables (users, songs, artists, time) using a dimension operator (load_dimension.py).

I implemented a data quality operator (data_quality.py) to check that tables are not empty and required fields have no null values.

I defined the pipeline in an Airflow DAG (etl_dag.py) to manage task dependencies and execution order.

Finally, I deployed and tested the pipeline using the Airflow UI, confirming that the data was processed and loaded correctly.
