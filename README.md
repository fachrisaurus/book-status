tolong buatkan saya terraform di region us-east-1

1. VPC name: techno-fachri
with a CIDR block of 25.1.0.0/16 and an IPv6 range provided by Amazon

2. Public Subnet name: techno-public-subnet
IPv4 CIDR ranges 25.1.0.0/24 and 25.1.2.0/24 and IPV6 /64

3. Private Subnet name: techno-private-subnet
IPv4 CIDR ranges 25.1.1.0/24 and 25.1.3.0/24

4. Public Route Table name: techno-public-rt

5. Private Route Table name: techno-private-rt

6. NAT Gateway name: techno-nat-gateway

7. SG
a. techno-sg-alb, allow incoming traffic on port 80 (HTTP) and port 443 (HTTPS) to public access
b. techno-sg-apps, open port 2000 to public access

8. S3
a. technoinput-malang-fachri
b. technooutput-malang-fachri

9. DynamoDB name: Tokens
partition key named token of type String

10. Kinesis DataStream name: technoinput-kinesis-fachri
The stream must be configured with Provisioned capacity mode
the user must provision 1 shard, which provides a baseline throughput of 1 MB/sec for write and 2 MB/sec for read operations

11. AWS Glue
a. database name: rekognition_results_db
b. table name: rekognition_results_table
The source data for this Glue table is in the S3 bucket s3://technooutput-malang-fachri/results
c. Glue Crawler name: techno-crawler-fachri


Simple Notifications Services (SNS)

LAMBDA FUNCTION

API Gateway Service
