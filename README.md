# SRJ-data-engineering-project
Data engineering project using Azure ADF and databricks

--> Create resource group in Azure.

--> Create resources :
          --> storage account ( datalake )
          --> ADF

--> Create Linked Services in Azure to establish connection from github to Azure for copying data and also connection to our created storage account in azure.

--> Create dynamic pipelines in ADF to copy data from github to bronze/raw layer container in storage account :
          --> Create dynamic pipeline to copy all the files from http location to azure lake area
          --> store all dynamic parameters like relativeURL , directoryName/FileName to be created in azure data lake in a json file (refer parameter/parameter-to-copy.json)
          --> create a lookup to look the json file and store it in json as value
          --> create a for Each to loop on all values and move the copy data pipeline inside it
          --> in all the dynamic parameters of copy job add dynamic variables from eachloop with the corresponding key in json to fetch the value dynamically
