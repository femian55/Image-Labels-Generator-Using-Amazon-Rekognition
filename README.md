# Build-An-Image-Labels-Generator-Using-Amazon-Rekognition
Build an image labels generator using Amazon Rekognition using the management console.

# Image Labels Generator using Amazon Rekognition

## Overview of Project ☁️

In this project, we will be building an image labels generator using Amazon Rekognition. This tool will recognize and label images. For example, if you have a photo of a cat, Amazon Rekognition will be able to identify and label the image as a cat. This project is both fun and educational, demonstrating the power of AWS services.

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

