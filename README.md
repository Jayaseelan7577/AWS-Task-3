# AWS Task-3

## Task Overview

This project demonstrates:

1. Amazon S3 bucket creation with public access blocked.
2. S3 file upload and CloudTrail/CloudWatch logging.
3. Two EC2 web servers running Nginx.
4. Application Load Balancer configuration.
5. Target group and health checks.
6. Traffic distribution between two EC2 web servers through the Application Load Balancer.

## AWS Services Used

- Amazon S3
- Amazon EC2
- AWS CloudTrail
- Amazon CloudWatch Logs
- Application Load Balancer
- Target Groups
- Nginx

## S3 Configuration

- S3 bucket: monitoring-task-s3-1789825168
- Public access: Blocked
- Test files uploaded successfully.
- CloudTrail S3 object-level data events enabled.
- CloudTrail events delivered to CloudWatch Logs.

## CloudWatch Verification

The S3 upload was verified using a CloudTrail `PutObject` event in CloudWatch Logs.

The event confirmed:

- Event source: Amazon S3
- Event name: PutObject
- Object: cloudwatch-test-file.txt
- Event category: Data
- HTTP status: 200

## EC2 Web Servers

### Web Server 1

- Instance: i-03e950d4abf556533
- Nginx configured on port 80
- Response identifies Web Server 1

### Web Server 2

- Instance: i-09331e0f15171a8d0
- Nginx configured on port 80
- Response identifies Web Server 2

## Application Load Balancer

- Name: aws-task-3-alb
- Type: Application Load Balancer
- Scheme: Internet-facing
- Listener: HTTP port 80
- Target Group: aws-task-3-targets

Both EC2 instances were verified as healthy targets.

## Load Balancer Traffic Test

The ALB DNS endpoint was tested with multiple HTTP requests.

The responses were successfully distributed between:

- Web Server 1
- Web Server 2

This verifies that traffic is reaching the EC2 instances through the Application Load Balancer.

## Screenshots

All task output screenshots are stored in the `screenshots` directory.
