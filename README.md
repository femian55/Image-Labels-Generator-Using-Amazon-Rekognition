# Image Labels Generator with Amazon Rekognition
Project Overview

This project demonstrates how to build an Image Labels Generator using Amazon Rekognition. The tool analyzes images and automatically generates descriptive labels.

For example: if you upload a picture of a cat, Rekognition can detect and label it as “Cat”. This project highlights the power of AWS AI/ML services in a practical, fun, and educational way.

 ## Services Used

- **Amazon S3**: For storing the images in the process of generating labels.
- **Amazon Rekognition**: To analyze images and generate image labels.
- **AWS CLI**: For interacting with AWS services through the command line interface (CLI).

  
## Prerequisites

Before starting, the following are reuire.
- An AWS account.
- AWS CLI installed and configured with AWS credentials.
- Python installed on local machine.

 
## Implementation Steps

The following steps are to be performed

### 1. Creating an Amazon S3 Bucket

1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the S3 service.
3. Click on "Create bucket".
4. Enter a unique bucket name and choose a region.
5. Leave the default settings and click "Create bucket".

### 2. Uploading Images to the S3 Bucket

1. Navigate to your newly created S3 bucket.
2. Click on "Upload" and add your images.
3. Click "Upload" to start the upload process.

### 3. Installing and Configuring the AWS Command Line Interface (CLI)

1. Install the AWS CLI from the [official website](https://aws.amazon.com/cli/).
2. Configure the CLI AWS credentials:
    ```bash
    aws configure
    ```
   Enter the Access Key ID, Secret Access Key, region, and output format.

### 4. Importing Libraries
### 5. Add Rekognition Logic
### 6. Define a detect_labels function to call Rekognition.
### 7. Define a main function to process images.
### 8. Run the Python script image_labels_generator.py to generate labels.

## Outcome
This automatically generate labels for any uploaded images. This enables to integrate Amazon Rekognition with S3 and Python.


The full python script are below

Create a new Python file, `image_labels_generator.py`, and import the required libraries:

```python
import boto3
import json
rekognition_client = boto3.client("rekognition")

def detect_labels(bucket, photo, max_labels=10, min_confidence=70):
    response = rekognition_client.detect_labels(
        Image={"S3Object": {"Bucket": bucket, "Name": photo}},
        MaxLabels=max_labels,
        MinConfidence=min_confidence,
    )

    print(f"\nDetected labels for {photo}:\n")
    for label in response["Labels"]:
        print(f"{label['Name']} ({label['Confidence']:.2f}%)")

    return response["Labels"]

def main():
    bucket_name = "your-s3-bucket-name"
    photo_name = "your-image-file.jpg"

    labels = detect_labels(bucket_name, photo_name)
    print("\n--- JSON Response ---")
    print(json.dumps(labels, indent=4))

if __name__ == "__main__":
    main()







