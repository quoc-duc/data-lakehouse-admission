# Data Lakehouse for University Admission Data

This project is about building a **Data Lakehouse architecture** to store and analyze university admission data.  

## Features
- Collect admission data (crawl from official sources or archives).
- Store data in a Data Lakehouse using Delta Lake on top of Apache Spark.
- Query and manage data with Apache Kyuubi.
- Visualize results with Power BI or other BI tools.

## Tech Stack
- **Docker + Docker Compose**
- **Apache Spark**
- **Delta Lake**
- **Apache Kyuubi**
- **MinIO (S3-compatible storage)**
- **Power BI**

## Versions

### Docker Images

| Image         | Version                      |
| ------------- | ---------------------------- |
| minio         | RELEASE.2024-01-13T07-53-03Z |
| minio/mc      | RELEASE.2024-01-13T08-44-48Z |
| postgres      | 10-alpine                    |
| apache/hive   | 3.1.3                        |
| bitnami/spark | 3.4.2                        |
| apache/kyuubi | 1.8.0-spark                  |

### Libraries on Containers

| Dependencies  | MinIO       | Hive        | Spark                 | Kyuubi                |
| ------------- | ----------- | ----------- | --------------------- | --------------------- |
| Hadoop Common | -           | 3.1.0       | 3.3.6                 | 3.3.6                 |
| Hadoop AWS    | -           | 3.1.0       | 3.3.6                 | 3.3.6                 |
| AWS SDK Bundle| -           | 1.11.271    | 1.12.367              | 1.12.367              |
| Delta Lake    | -           | -           | delta-core_2.12:2.4.0 | delta-core_2.12:2.4.0 |
| Apache Spark  | -           | -           | 3.4.1                 | 3.4.1                |

## How to run ?

### Pre-requisites

* Create folder hadoop-libs in the project root
* Download [AWS Java SDK Bundle 1.11.271](https://medium.com/r/?url=https%3A%2F%2Frepo1.maven.org%2Fmaven2%2Fcom%2Famazonaws%2Faws-java-sdk-bundle%2F1.11.271%2Faws-java-sdk-bundle-1.11.271.jar) and [Hadoop AWS 3.1.0](https://medium.com/r/?url=https%3A%2F%2Frepo1.maven.org%2Fmaven2%2Forg%2Fapache%2Fhadoop%2Fhadoop-aws%2F3.1.0%2Fhadoop-aws-3.1.0.jar)
* Place jars in hadoop-libs folder

Use Docker Compose:

```bash
docker compose up
```

## How to shut down and clean-up ?

Use Docker Compose:

```bash
docker compose down -v
```
