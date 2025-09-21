# Image Labels Generator with Amazon Rekognition
Project Overview

This project demonstrates how to build an Image Labels Generator using Amazon Rekognition. The tool analyzes images and automatically generates descriptive labels.

For example: if you upload a picture of a cat, Rekognition can detect and label it as “Cat”. This project highlights the power of AWS AI/ML services in a practical, fun, and educational way.
## Steps to be performed 👩‍💻

In the next few lessons, we'll be going through the following steps:

1. [Creating an Amazon S3 Bucket](#creating-an-amazon-s3-bucket)
2. [Uploading Images to the S3 Bucket](#uploading-images-to-the-s3-bucket)
3. [Installing and Configuring the AWS Command Line Interface (CLI)](#installing-and-configuring-the-aws-command-line-interface-cli)
4. [Importing Libraries](#importing-libraries)
5. [Adding `detect_labels` Function](#adding-detect_labels-function)
6. [Adding Main Function](#adding-main-function)
7. [Running Your Python File](#running-your-python-file)

## Services Used 🛠

- **Amazon S3**: For storing the images in the process of generating labels.
- **Amazon Rekognition**: To analyze images and generate image labels.
- **AWS CLI**: For interacting with AWS services through the command line interface (CLI).

## Prerequisites

Before starting, ensure you have the following:

- An AWS account.
- AWS CLI installed and configured with your AWS credentials.
- Python installed on your local machine.

## Steps

### Creating an Amazon S3 Bucket

1. Log in to the [AWS Management Console](https://aws.amazon.com/console/).
2. Navigate to the S3 service.
3. Click on "Create bucket".
4. Enter a unique bucket name and choose a region.
5. Leave the default settings and click "Create bucket".

### Uploading Images to the S3 Bucket

1. Navigate to your newly created S3 bucket.
2. Click on "Upload" and add your images.
3. Click "Upload" to start the upload process.

### Installing and Configuring the AWS Command Line Interface (CLI)

1. Install the AWS CLI from the [official website](https://aws.amazon.com/cli/).
2. Configure the CLI with your AWS credentials:
    ```bash
    aws configure
    ```
   Enter your Access Key ID, Secret Access Key, region, and output format.

### Importing Libraries

Create a new Python file, `image_labels_generator.py`, and import the required libraries:

```python
import boto3
import json

