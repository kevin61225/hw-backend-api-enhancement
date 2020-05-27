# Assignment - API Enhancement

## Scenario

There is a legacy website written in PHP without any framework and the codes are quite messy.  
Recently, users are complaining about the pool perfomance on pages related to their usage data on Amazon Web Service.  
After an investigation, you found the current PHP fetches all data at once on the page, which is a bad implementation.  

To resolve this issue, you decide to use __ajax__ to perform API calls for paginated data, which can reduce the response time. Please see the target section down below and try to implement all of them.

## Target

1. Import csv file into database, choose any service you want. e.g. Amazon RDS, Azure SQL Databae.
2. Make an API to __list records__ in database.
3. You can only use ajax to performace API calls.
4. *(Optional)* Use your algorithm to reduce response time when calling the API.

## Deliverable

1. Upload codes to your __GitHub__ and __provide repo URL__.
2. *(Optional)* Host your codes on any cloud service, e.g. __Heroku__, __Amazon Web Serivce (AWS)__, __Microsoft Azure__, __Google Cloud Platform (GCP)__, and __provide site URL__.   
    * If you are using __AWS__ / __Azure__ / __GCP__, describe what services you are using. 

## Notice

* Once you finished the assignment, send an email back to the one who contacted you.
* Leave comments to __README.md__ in __the root of your repo__ if there is any.
