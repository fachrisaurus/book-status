tolong buatkan saya terraform di region us-east-1
catatan: role yang digunakan hanya arn:aws:iam::488665884770:role/LabRole

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
bucket policy must be applied to allow public read access where appropriate —
particularly for assets that need to be accessed by users or external systems. This 
involves careful configuration of the policy JSON to avoid security 
misconfigurations while enabling necessary access. Users are encouraged to refer 
to the AWS documentation on S3 Bucket Policies to ensure compliance and 
proper implementation

9. DynamoDB name: Tokens
partition key named token of type String

10. Kinesis DataStream name: technoinput-kinesis-fachri
The stream must be configured with Provisioned capacity mode
the user must provision 1 shard, which provides a baseline throughput of 1 MB/sec for write and 2 MB/sec for read operations

11. AWS Glue
a. database name: rekognition_results_db
b. table name: rekognition_results_table
The source data for this Glue table is in the S3 bucket s3://technooutput-malang-fachri/results
This path is expected to contain JSON files or similar formats resulting from image analysis or machine learning processes.

c. Glue Crawler name: techno-crawler-fachri
This crawler is responsible for automatically detecting the schema of the data stored in the S3 location and updating the rekognition_results_table accordingly. The crawler should be 
scheduled or triggered based on data arrival patterns to ensure the catalog remains up to date and queryable in near real-time


12. Simple Notifications Services (SNS) name: techno-sns-malang-fahri
Once the topic is created, an email subscription must be configured so that all 
messages published to the topic are delivered to the following address:
handi@seamolec.org.

13. REST API Gateway Service name: 
regional endpoint type and use IPV4 and IPV6
The API should have the following resources and 
methods:
- A resource named /generate-token, with the following HTTP methods:
o POST (/generate-token /POST) to create a new token
- A resource named /validate-token, with the following HTTP methods:
o GET (/validate-token /GET) to validate token.

