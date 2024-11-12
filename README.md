# AWS-S3-Snowflake-Integration
Project integrating AWS S3 with Snowflake for data loading and transformation.


## Project Description
This project demonstrates how to integrate an AWS S3 bucket with Snowflake by creating stages, defining file formats, and performing data loading and transformations. The goal is to enable seamless data transfer and updates between S3 and Snowflake.

## Prerequisites
- AWS Account with appropriate permissions
- Snowflake Account with admin privileges
- AWS CLI and SnowSQL installed

## Project Setup

### Step 1: Set Up IAM Roles and Policies
- Create an IAM role in AWS with S3 read/write access.
- Attach the necessary policies to allow Snowflake to access the S3 bucket.
- Refer to `aws_config/IAM_roles_policies.md` for details on the IAM role setup.

### Step 2: Configure S3 Bucket
- Create an S3 bucket and upload the data files to be loaded into Snowflake.
- Refer to `aws_config/s3_bucket_setup.md` for setup instructions.

### Step 3: Configure Snowflake
- Set up a stage in Snowflake to connect with the S3 bucket.
- Define the file format for data ingestion.
- Use the SQL scripts in `snowflake_config/`:
  - `create_stage.sql` to create a stage in Snowflake.
  - `file_format.sql` to define the file format.
  - `load_data.sql` to load and transform data from S3 to Snowflake.

## Usage
1. Upload your data file to the S3 bucket.
2. Execute the SQL scripts in Snowflake to load data and perform transformations.
3. Any changes in the S3 bucket (additions, removals) will reflect in Snowflake upon reloading.

## Security Considerations
- Ensure credentials and sensitive information are stored securely.
- Avoid hard-coding credentials; instead, use environment variables or IAM roles with appropriate permissions.

