# Formula 1 Analytics on AWS

For my CSC 254 capstone, I built an AWS analytics pipeline for Formula One World Championship data covering 1950–2023. I used Amazon Athena to explore the data with SQL, then built an interactive Amazon QuickSight dashboard focused on sprint results and pit stops.

[Download the project presentation, including console and dashboard screenshots](docs/aws-f1-analytics.pptx)

## How the data moves

| Stage | What I configured |
| --- | --- |
| Storage | Uploaded the Formula 1 CSV files to Amazon S3. |
| Cataloging and preparation | Configured an AWS Glue crawler to discover schemas and register tables in the Glue Data Catalog database `f1-database`. I also created a Glue ETL job for data preparation. |
| SQL analysis | Queried the S3-backed tables in Amazon Athena and created a SQL view. |
| Visualization | Built QuickSight visuals from sprint results and pit stop records. Slide 8 shows the Formula 1 dashboard. |

## Access and auditing

I enabled S3 Block Public Access and used SSE-S3 encryption for the bucket. I configured CloudTrail for auditing and created IAM roles with permissions for the resources each service needed.

## Project evidence

Slides 5–7 document the Glue crawler, catalog tables, ETL job and Athena queries. Slides 10–11 cover security and IAM roles. The repository contains the original presentation. The underlying race data is available separately on Kaggle.

[Formula 1 World Championship dataset on Kaggle](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020)

**Author** · Llewellyn Forrester
