# Cloud Computing Project 2: Face Detection and Recognition System

This project implements a distributed face detection and recognition system using AWS cloud services. The system processes video frames to detect faces and recognize individuals using a serverless architecture.

## Project Overview

The system consists of two main components:
1. **Face Detection**: Detects faces in video frames using AWS Lambda
2. **Face Recognition**: Recognizes detected faces using AWS Lambda

### Architecture

- **AWS Services Used**:
  - AWS Lambda for serverless computing
  - Amazon S3 for storage
  - Amazon SQS for message queuing
  - Amazon DynamoDB for data persistence
  - Amazon CloudWatch for monitoring

### Directory Structure

```
cloud-computing-project2/
├── src/
│   ├── face-detection/
│   │   └── fd_component.py
│   └── face-recognition/
│       └── fr_lambda.py
├── data/
│   └── sample_frames/  # Sample video frames for testing
└── docs/
    └── README.md
```

## Setup Instructions

1. **Prerequisites**:
   - AWS Account with appropriate permissions
   - Python 3.8 or higher
   - AWS CLI configured with appropriate credentials

2. **AWS Configuration**:
   - Create necessary IAM roles and policies
   - Set up S3 buckets for storing video frames and results
   - Configure DynamoDB tables
   - Set up SQS queues

3. **Deployment**:
   - Deploy Lambda functions using AWS Console or AWS CLI
   - Configure environment variables for Lambda functions
   - Set up CloudWatch alarms and monitoring

## Usage

1. Upload video frames to the designated S3 bucket
2. The system will automatically:
   - Detect faces in the frames
   - Recognize individuals in the detected faces
   - Store results in DynamoDB
   - Generate output files

## Implementation Details

### Face Detection Component
- Processes video frames from S3
- Uses OpenCV for face detection
- Sends detected faces to SQS for recognition

### Face Recognition Component
- Receives face images from SQS
- Performs face recognition
- Stores results in DynamoDB

## Security Considerations

- All AWS credentials should be managed through IAM roles
- S3 buckets should have appropriate access policies
- Lambda functions should have minimal required permissions
- Sensitive data should be encrypted

## Monitoring and Logging

- CloudWatch metrics for system performance
- Lambda function logs for debugging
- SQS queue monitoring
- DynamoDB table metrics

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is part of the CSE546 Cloud Computing course at Arizona State University.

## Acknowledgments

- AWS Documentation
- OpenCV Library
- Course Instructors and TAs 