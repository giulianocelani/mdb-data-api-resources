# mdb-data-api-resources

> **Disclaimer**: This API is in BETA and resources could most likely be modified

This repo contains files that can be used to import into Postman to easily request the resources provided in the [MongoDB Atlas Data API](https://docs.atlas.mongodb.com/api/data-api-resources/).

## Description

Contains two useful files 

- Postman **Collection** which contains the available resources which can be requested

    [mdb-data-api.postman_collection.json](mdb-data-api.postman_collection.json)

- Postman **Environment** which contains user specific variables that are needed for each resource

    [mdb-data-api.postman_environment.json](mdb-data-api.postman_environment.json)

The above files can be directly imported into Postman so that you can read and manipulate your data stored in MongoDB Atlas

Following CRUD operations supported

- `findOne` / `find`
- `insertOne` / `insertMany`
- `updateOne` / `updateMany`
- `replaceOne`
- `deleteOne` / `deleteMany`
- `aggregate`

## Setup

1. **Install Postman**
    - [Download](https://www.postman.com/downloads/) and install on your local machine
  
2. **Provision MongoDB Atlas Cluster**

    If a Atlas cluster is not yet provisioned, go ahead a create one via the [Atlas UI](https://docs.atlas.mongodb.com/getting-started/)

3. **Enable Data API**

    1. Click **Data API** in the left navigation menu in Atlas. On the following screen, select one or more clusters that you want to enable the API on from the dropdown menu and then click **Enable the Data API**. 
    2. When you enable the **Data API**, make sure to create click **Create API Key**, enter a unique name for the new key, and then save. 
   
        - **NOTE:** Store the returned value for later use.

4. **Import into Postman**
   
    - There is two options, both explained with more detail in the [postman learning centre](https://learning.postman.com/docs/getting-started/importing-and-exporting-data/#importing-data-into-postman)

        1. Import via Github
            - Fork this repository
            - Import the code repository into postman
        2. Import raw `.json` files
            - Download the necessary `.json` files from this repo
            - Import the `.json` files 

5. **Populate your Postman Environment**

    - Make sure to be in the correct Postman Workspace where you imported the **collection** and **environment**
    - Click **Environments** in the left navigation in Postman.
    - Navigate to `MDB-Data-API` and populate the following
      - `DATA_API_APP_ID`\: Found in the URL provided in the UI
    
          `https://data.mongodb-api.com/app/<DATA_API_APP_ID>/endpoint/data/beta`
    
      - `API_KEY`: Created API Key in the Atlas UI
      - `CLUSTER_NAME`: Desired data source (cluster name)
      - `DATABASE`: Desired target database
      - `COLLECTION`: Desired target collection
    - Make sure the environment is [active](https://learning.postman.com/docs/sending-requests/managing-environments/#selecting-an-active-environment)

6. **Start request with Postman**

    - Click **Collections** in the left navigation in Postman.
    - Navigate to `MDB-Data-API` 
    - You are all setup and can now start requesting the available resources with the Atlas Data API