# Assignment - API Enhancement

## Description

Please see the target section down below and try to achieve the items as many as you can.

## Target

1. Import csv file into database, your table __MUST__ have the following columns down below. You can choose any Database service you want. e.g. __Amazon RDS__, __Azure SQL Databae__ or __local SQLite__.

      | Column | Description |
      | -- | -- |
      | bill/PayerAccountId | The account ID of the paying account. For an organization in AWS Organizations, this is the account ID of the master account. |
      |lineItem/UnblendedCost | The UnblendedCost is the UnblendedRate multiplied by the UsageAmount. |
      | lineItem/UnblendedRate | The uncombined rate for specific usage. For line items that have an RI discount applied to them, the UnblendedRate is zero. Line items with an RI discount have a UsageType of Discounted Usage. |
      | lineItem/UsageAccountId |The ID of the account that used this line item. For organizations, this can be either the master account or a member account. You can use this field to track costs or usage by account. |
      | lineItem/UsageAmount | The amount of usage that you incurred during the specified time period. For size-flexible reserved instances, use the reservation/TotalReservedUnits column instead. |
      | lineItem/UsageStartDate |  The start date and time for the line item in UTC, inclusive. The format is YYYY-MM-DDTHH:mm:ssZ. |
      | lineItem/UsageEndDate | The end date and time for the corresponding line item in UTC, exclusive. The format is YYYY-MM-DDTHH:mm:ssZ. |
      | product/ProductName | The full name of the AWS service. Use this column to filter AWS usage by AWS service. Sample values: AWS Backup, AWS Config, Amazon Registrar, Amazon Elastic File System, Amazon Elastic Compute Cloud |
      
2. Create DB index to enhance query performance.
3. Make APIs to achieve the following requirements
    1. Get __lineItem/UnblendedCost__ grouping by __product/productname__
        - Input
          | Column | Required |
          | ------ | -------- |
          | lineitem/usageaccountid | true |
        - Output 
        ```JSON
            {
                "{product/productname_A}": "sum(lineitem/unblendedcost)",
                "{product/productname_B}": "sum(lineitem/unblendedcost)",
                ...
            }
        ```
    1. Get daily __lineItem/UsageAmount__ grouping by __product/productname__
        - Input
          | Column | Required |
          | ------ | -------- |
          | lineitem/usageaccountid | true |
        - Output
        ```JSON
            {
                "{product/productname_A}": {
                    "YYYY/MM/01": "sum(lineItem/UsageAmount)",
                    "YYYY/MM/02": "sum(lineItem/UsageAmount)",
                    "YYYY/MM/03": "sum(lineItem/UsageAmount)",
                    ...
                },
                "{product/productname_B}": {
                    "YYYY/MM/01": "sum(lineItem/UsageAmount)",
                    "YYYY/MM/02": "sum(lineItem/UsageAmount)",
                    "YYYY/MM/03": "sum(lineItem/UsageAmount)",
                    ...
                },
            }
        ```
4. Your can only use __Python__ or __C#__ to implement APIs.
5. *(Optional)* You __can add more input arguments__ to your APIs to achieve paginaton strategy.
6. *(Optional)* Use your algorithm to reduce response time when calling the APIs.

## Deliverable

1. Upload codes to your __GitHub__ and __provide repo URL__.
2. Include a __README.md__ file in __the root of repo__.
3. Provide your __API spec__, __API URLs__, and __DB schema__ to __README.md__.
4. Use any kind of framework, e.g. Laravel, CakePHP, Django, Flask.
5. *(Optional)* If you are using __AWS__ / __Azure__ / __GCP__, describe what services you are using. 
6. *(Optional)* Describe how you reduce the response time / improve performance to __README.md__.

## Notice

* Once you finished the assignment, send an email back to the one who contacted you.
* Leave comments to __README.md__ if there is any.
