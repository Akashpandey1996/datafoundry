# The Data Foundry Technical Challenge

This is a technical challenge to ingest data from an API of your choosing into AWS S3.

## Things To Note During API Data Pull

### Pagination:
    Pulling Data in chunk and not at once to keep low load. 
### Storing Data in memory:
    We can store data in memory if the data is small, makes it faster to re process the data. Eliminates usage of files.
### Retry:
    We can specify a limit to number of retris in case of a faliure.

     