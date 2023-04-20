# The Data Foundry Technical Challenge

This is a technical challenge to ingest data from an API of your choosing into AWS S3.

## Things To Note During API Data Pull

### Pagination:
    Pulling Data in chunk and not at once to keep low load. 
### Storing Data in memory:
    We can store data in memory if the data is small, makes it faster to re process the data. Eliminates usage of files.
### Retry:
    We can specify a limit to number of retris in case of a faliure.

## Steps Taken To Perform The Task
* Lambda_function.py
  - Created a lambda handler function that call all other functions.
  - gets_number_of_records to be downloaded in chunks.
  - downloads the data into a local file using the API.
  - Attaches unique keys to every file. 
  - Gets file from local directory and pushes to the s3 bucket.

* setup_infra.sh
  - Creating local configuration files.
  - Creating the Bucket.
  - Creating policy, role and attaching policy to the role.
  - Creating the lambda function and scheduling it using the cloudwatch every 30 mins.
  - Attaching lambda function to event and then to the rule.