# spotify-data-processing-data-engineering-project

## Introduction
This project utilizes AWS services to extract, transform, and analyze Spotify data. It leverages AWS Lambda for data processing, Amazon S3 for storage, AWS Glue for data cataloguing, and Amazon Athena for querying. 

## Overview

The project utilizes the following AWS services:

- **AWS Lambda**: For data extraction and transformation.
- **Amazon CloudWatch**: To trigger Lambda functions on a scheduled basis.
- **Amazon S3**: For storing raw and transformed data.
- **AWS Glue**: For inferring schema and creating a data catalog.
- **Amazon Athena**: For querying the data stored in S3.

## Architecture

<img width="400" alt="Spotify_Architecture_Diagram" src="https://github.com/YaguPatel/spotify-data-processing-data-engineering-project/assets/137278772/3da81205-7a83-4265-b82f-a553410daa17">


1. **Data Extraction**: AWS Lambda function is triggered daily via Amazon CloudWatch to extract data from the Spotify API. Extracted data is stored in Amazon S3 (raw data).

2. **Data Transformation**: Another Lambda function is triggered by S3 object put event. It transforms the raw data and stores it in another Amazon S3 bucket (transformed data).

3. **Data Cataloging**: AWS Glue infers schema of the transformed data stored in S3, creating a data catalog.

4. **Querying**: Amazon Athena is used to query the data directly in S3 using standard SQL queries.

## Usage

1. Clone the repository:
