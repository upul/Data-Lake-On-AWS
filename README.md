# Building a Data Lake on AWS

The scope of the project is to create an data lake for a music application. The source data are stored in a bunch of JSON files in AWS S3 buckets. We process them and extract useful information about users, songs, artists, users' listing information. Next, push extracted data to the data lake for further analysis.

## Project Structure

My project contains the following three files.

* `etl.py`: contains main ETL logic
* `dl.cfg`: AWS credentials
* `README.md`: useful information about setting up the project and running the ETL pipeline.

## How to Run the Project?

* Update `dl.cfg` file with your AWS access key and secret key. 
* Create an S3 bucket called s3a://upulbandara-dend
* Run the ETL process using the following command

```bash
python etl.py
```


## ETL pipeline consists of four distinct steps.

* **Step 1**: Read AWS credentials from the dl.cfg file.
* **Step 2**: Read source data from S3: s3a://udacity-dend/song_data and s3a://udacity-dend/log_data 
* **Step 3**: Read data into spark Data Frame and create five separate tables. 
* **Step 4**: Save those five tablets into the S3 bucket as parquet files.  s3a://upulbandara-dend/