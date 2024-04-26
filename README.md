# AWS CI/CD for KCD Pune Website

This repository contains the configuration files and setup instructions for implementing Continuous Integration (CI) and Continuous Deployment (CD) for the KCD Pune website using AWS services with a static S3 website hosting.

## Overview

The CI/CD pipeline automates the process of building, testing, and deploying updates to the KCD Pune website hosted on AWS S3. It utilizes the following AWS services:

- AWS CodePipeline: Orchestrates the CI/CD workflow.
- AWS CodeBuild: Builds the website from source code.
- AWS S3: Hosts the static website.
- AWS CloudFront (optional): CDN for caching and improving website performance.

## Setup Instructions

### Prerequisites

Before setting up the CI/CD pipeline, ensure you have the following:

- An AWS account with appropriate permissions to create and manage CodePipeline, CodeBuild, and S3 resources.
- Source code of the KCD Pune website stored in a version control system (e.g., GitHub).

Certainly! Here are the steps broken down in a more detailed and sequential manner:

### Step 1: Set Up AWS Resources

1. **Create S3 Bucket**:
    - Enable static website hosting in the bucket properties

2. **Create IAM Role**:
    - Create a new IAM role with the necessary permissions for CodePipeline, CodeBuild, and S3.
    - Attach the IAM role to the pipeline and build project.

### Step 2: Configure CodePipeline

1. **Create CodePipeline**:
    - Navigate to the CodePipeline service.
    - Click on "Create pipeline".
    - Define a pipeline name and select the source provider (e.g., GitHub).
    - Configure the source settings to connect to your repository.
    - Add a build stage and select CodeBuild as the build provider.
    - Configure the build settings, including the buildspec file location.
    - Add a deploy stage and select Amazon S3 as the deployment provider.
    - Specify the S3 bucket and object key for deployment.

### Step 3: Setup CodeBuild

1. **Define Build Specification**:
    - Create a `buildspec.yml` file in the root of your repository.
    - Specify the build commands, such as compiling assets or running tests.

2. **Configure CodeBuild**:
    - Navigate to the CodeBuild service.
    - Create a new build project.
    - Define a project name and source settings (GitHub repository).
    - Configure the build environment and specify the buildspec file location.
    - Attach the previously created IAM role to the build project.

### Step 4: Test the Pipeline

1. **Trigger Pipeline**:
    - Manually trigger the pipeline execution to test the workflow.
    - Verify that the source code is pulled, built, and deployed successfully.
    - Monitor the pipeline execution for any errors or issues.

2. **Automate Triggers**:
    - Set up automatic triggers based on code changes.
    - Ensure that the pipeline automatically executes whenever there's a new commit or pull request.

### Step 5: Access the Website

1. **Access via S3 URL**:
    - Once the deployment is successful, access the KCD Pune website using the S3 bucket's static website URL.
    - If using CloudFront, access the website using the CloudFront distribution URL.




