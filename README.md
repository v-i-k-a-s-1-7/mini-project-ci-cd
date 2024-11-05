# Automated Deployment Pipeline for a Web Application

This project demonstrates a Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins, Docker, and AWS EC2. The goal is to automate the deployment of a simple web application on an EC2 instance, providing hands-on experience with DevOps tools and practices.

## Project Overview

The project sets up a fully automated pipeline where:
- A web application is created and dockerized.
- Jenkins is configured to monitor a Git repository for changes.
- Jenkins builds a Docker image of the app, pushes it to a registry, and deploys it to an EC2 instance.

### Key Tools
- **Jenkins**: For automating the build, test, and deployment processes.
- **Docker**: To containerize the application and make deployment consistent across environments.
- **AWS EC2**: Instances for hosting Jenkins and the deployed application.

## Project Setup

Follow these steps to recreate the setup:

### 1. Create and Dockerize the Web Application
   - Develop a basic web application in Node.js or Python.
   - Write a `Dockerfile` to package the app into a Docker image.
   - Push the app code to a GitHub repository.

### 2. Set Up Jenkins on an EC2 Instance
   - Launch an EC2 instance and install Jenkins.
   - Configure Jenkins, including necessary plugins for Docker and Git.
   - Add an SSH key to allow Jenkins access to other EC2 instances for deployment.

### 3. Configure Jenkins Pipeline
   - Set up a Jenkins pipeline job that:
     - Pulls the latest code from the Git repository.
     - Builds a Docker image based on the `Dockerfile`.
     - Pushes the Docker image to Docker Hub or a private registry.

### 4. Set Up Deployment Server on EC2
   - Launch another EC2 instance to serve as the deployment environment.
   - Install Docker on this instance to enable running the Dockerized app.
   - Ensure SSH access between this instance and Jenkins.

### 5. Automate Deployment Using Jenkins
   - Add a deployment stage to the Jenkins pipeline:
     - SSH into the deployment server.
     - Pull the Docker image from the registry.
     - Run the Docker container to deploy the app.

### 6. Test the Pipeline
   - Verify that the pipeline correctly builds, pushes, and deploys the app when changes are committed to the Git repository.

## Project Outcome

This project provides hands-on experience in:
- Setting up CI/CD with Jenkins and Docker.
- Deploying containerized applications on AWS EC2.
- Automating end-to-end deployment for efficient DevOps workflows.

## Prerequisites

- Basic knowledge of Jenkins, Docker, and AWS EC2.
- A GitHub account and repository for storing the web application code.
- AWS account with EC2 access.

## Usage

1. Clone the repository and make changes to the web application code.
2. Push updates to the Git repository.
3. Jenkins will detect the changes, rebuild the Docker image, and deploy the new version to the EC2 instance automatically.

