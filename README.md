# Spotify-End-to-End-Data-Engineering-Project

### Introduction
In this project, I Built an ETL(Extract,Transform,Load) pipeline using the Spotify API. The pipeline will retrieve data from the spotify API, transformed it to a desired format and load data at the end.
## Architecture

![Architecture diagram](https://github.com/DerickAlex/spotify-end-to-end-data-engineering-project/blob/main/Architecture%20Diagram.PNG)

### Dataset Used/API
This API contains information about music,artists,albums and songs [Spotify-API-Doc](https://developer.spotify.com/documentation/web-api)

### Services Used
1. **S3** - Amazon S3 is object storage built to store and retrieve any amount of data from anywhere. S3 is a simple storage service that offers industry leading durability, availability, performance, security, and virtually unlimited scalability at very low costs.
2. **AWS Lambda** - AWS Lambda is a serverless, event-driven compute service that lets you run code for virtually any type of application or backend service without provisioning or managing servers.
3. **CloudWatch** -  Amazon CloudWatch collects and visualizes real-time logs, metrics, and event data in automated dashboards to streamline your infrastructure and application maintenance.
4. **Glue Crawler** -  A crawler is a job defined in Amazon Glue. It crawls databases and buckets in S3 and then creates tables in Amazon Glue together with their schema.Then, you can perform your data operations in Glue, like ETL.
5. **Data Catalog** - A data catalog uses metadata—data that describes or summarizes data—to create an informative and searchable inventory of all data assets in an organization.
6. **Amazon Athena** -  Amazon Athena enables users to analyze data in Amazon S3 using Structured Query Language (SQL). The tool is designed for quick, ad hoc and complex analysis

### install packages
```
pip install pandas
pip install numpy
pip install spotipy
```
### Project Execution Flow
Extract Data From API --> Lambda Trigger (Every 1 hour) --> Run Extract Code --> Store Raw Data -->T= Trigger Transform Function -->Transform Data and Load it --> Create a Glue Crawler --> Glue Catalog Created --> Athena for Querying Purposes
