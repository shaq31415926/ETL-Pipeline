# ETL Pipeline Project

## Project Description
The goal of the project is to build an ETL pipeline. ETL (Extract, Transform, Load) is a data pipeline used to collect data from various sources, transforms the data according to business requirements, and loads the data into a destination data storage.

This project contains the following python files:
- extract.py - contains functions to connect to Amazon Redshift data warehouse and to extract online transactions data with transformation tasks using SQL
- transform.py - contains function to identify and remove duplicated records
- load_data_to_s3.py - contains functions to connect to Amazon S3 cloud object storage and to write the cleaned data as a CSV file into an S3 bucket
- main.py - contains all instructions to extract, transform, and load the transformed data using the functions from extract.py, transform.py, and load_data_to_s3.py.

## Requirements
- Docker:
    - Docker for Mac: [Install Docker Desktop on Mac](https://docs.docker.com/desktop/install/mac-install/)
    - Docker for Windows: [Install Docker Desktop on Windows][https://docs.docker.com/desktop/install/windows-install/]
    - WSL2 Linux Kernel Update: [Download the Linux kernel update package](https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)

- Python 3.9 or higher

## How to Run the Project

- To run main.py on local terminal:
    - Windows: 
    ```
        python main.py
    ```
    - Mac: 
    ```
          python3 main.py
    ```

- To run using Docker
    - 1. Build an image
    ```
      docker image build -t etl-pipeline .
    ```
    - 2. Run the etl job
    ```
      docker run --env-file .env etl-pipeline
    ```