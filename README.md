# Quality Movie Data Ingestion (Mainatining of quality of data)
## Tech Stacks - AWS Glue, S3, SNS, Redshift, Cloudwatch, Data Quality Rule

### As this project is batch processing, per day we will be getting the dataset from IMDb, so we need to process it and ingest it in Redshift.
1. We consumed data from AWS S3.
2. We evaluated the data quality of the dataset to check if it suceeds or fails. We implemented few rules where we get to know that some rules will pass and some rules will fail.
3. Either proceed or terminate Glue Job if Data Quality fails, log it into EventBridge and get notified on SNS.
4. Passed records will be ingested in Redhsift.
5. Failed records are dumped in another S3 where on top of it we can create Athena table for querying and make the dashboard out of it for monitoring so that anything can be tracked precisely what is outgoing and what is incoming.
6. As soon as there's a system failure, we're getting notified in seconds and taking actions.




![Quality-Movie-Data-Ingestion](https://github.com/Kanthji/Quality-movie-data-ingestion/assets/116734498/0c3ebba9-1ec3-4632-8910-08d0bc6bf5da)
