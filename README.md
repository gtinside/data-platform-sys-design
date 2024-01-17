# data-platform-sys-design
System design of a distributed financial data platform

## Functional Requirements:
1. Process Files per dataset
    - Make the data available within SLA into the database
2. Notify the data providers and users if the data is invalid
3. Proactively notify the users if the data is running late
4. Run data quality checks post availability
## Non Functional Requirements
1. Scalability - System should be scalable as the number of files can increase significantly
2. Availability is more important than Consistency - This is an eventual consistent system
3. Durability - Files should not get lost
## Estimates
1. Datasets: 100
2. Average Daily Files per dataset: 10,000
3. Total Daily Files: 1 M 
4. 10 files processed per second
## Components
1. File Downloader
2. AWS S3 Buckets
3. Tracker Lambda(Kafka Producer)
4. Kafka Topics per dataset
5. ETL Service (Kafka Consumer)
6. Data Catalog Service
7. Notification Service
8. RDS 
9. DynamoDB
    - TrackingDB
    - Data Catalog
    - Dataset Metadata
## High Level Design
![alt text](/assets/sys-des.png "Data Platform")

