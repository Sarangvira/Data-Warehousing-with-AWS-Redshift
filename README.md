# Data-Warehousing-with-AWS-Redshift

This repo provides the ETL pipeline, to populate the sparkifydb database in AWS Redshift.

The purpose of this database is to enable Sparkify to answer business questions it may have of its users, the types of songs they listen to and the artists of those songs using the data that it has in logs and files. The database provides a consistent and reliable source to store this data.

This source of data will be useful in helping Sparkify reach some of its analytical goals, for example, finding out songs that have highest popularity or times of the day which is high in traffic.

## Files
create_tables.py is the python script that drops all tables and create all tables (including staging tables)

sql_queries.py is the python file containing all SQL queries. It is called by create_tables.py and etl.py

etl.py is the python script that loads data into staging tables, then load data into fact and dimension tables from staging tables

redshift_cluster_setup.py sets up the redshift cluster and creates an IAM role for redshift to access other AWS services

redshift_cluster_teardown.py removes the redshift cluster and IAM role created

## running the ETL pipeline

First, create_tables.py --  to create the data tables using the schema design specified. If tables were created previously, they will be dropped and recreated.

Next, etl.py -- to populate the data tables created.
