# Data-Analysis-of-Youtube

Dataset used from : https://www.kaggle.com/datasets/datasnaek/youtube-new

I developed a few KPIs to examine this data in order to compare channels in the UK and Canada's popularity, most popular video categories, video reach, and engagement.

I have prepared and analyzed the  YouTube Video  data from Kaggle for use in this project.
JSON and CSV files make up this dataset's two types of files. This is how it happens:
Step : 1	I attempted to preserve correct file organization while I used AWS CLI instructions to upload the data from my local PC into the S3 bucket. Separate folders were used to store the JSON and CSV files.

Step : 2	Utilized AWS Glue Catalog to crawl the data from the raw bucket's JSON and CSV files, which would then be placed in a different database.
Step : 3	Create a Python function using AWS Lambda to clean up the JSON data and convert it to parquet format whenever problems arise as a result of the JSON format.
Step : 4	This Lambda function had a trigger attached to it so that it would run each time new data was added to the S3 bucket, and the output was saved in a fresh database in Athena.
Step : 5	AWS Glue ETL was used to convert the CSV files into parquet format as well.
Step : 6	Generated a new Glue Crawler to enter the database with the clean data.
Step : 7	Once all the clean data from the parquet files (converted from CSV and JSON files) was available in the database, an ETL process was created using AWS Glue Studio to link the two tables and put the data in a different S3 bucket meant to be used for business intelligence.
Step : 8	The data is now prepared for use in creating dashboards.
