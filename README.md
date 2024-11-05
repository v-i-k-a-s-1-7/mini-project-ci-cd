# mini-project-ci-cd
# CI/CD Pipeline Demonstration Project

## Overview

This project is designed to demonstrate the setup and functionality of a CI/CD (Continuous Integration/Continuous Deployment) pipeline using Jenkins and Docker. It showcases how to automate the building, testing, and deployment of a Node.js application within a containerized environment.

## Key Concepts

- **CI/CD Pipeline**: Automates the process of building, testing, and deploying applications, ensuring rapid and reliable software delivery.
- **Docker**: Containerizes the application, ensuring consistent behavior across different environments.
- **Jenkins**: Manages the pipeline, automating each step of the build and deployment process.

## Pipeline Workflow

### 1. **Source Code Management**
   - The source code is maintained in a Git repository. Jenkins is configured to watch for changes in the repository.

### 2. **Jenkins Pipeline**
   - The CI/CD pipeline is defined in the `Jenkinsfile`, which automates the following steps:
     - **Build**: Jenkins clones the repository and initiates the build process.
     - **Docker Build**: A Docker image is built using the provided `Dockerfile`.
     - **Test (Optional)**: Although no specific tests are included, this step can be added to execute automated tests.
     - **Deploy**: The built Docker image is run in a container, exposing the application to the specified port (e.g., 3000).

### 3. **Docker Integration**
   - The project is containerized using Docker, ensuring consistency across development, testing, and production environments.
   - The `Dockerfile` defines the steps to set up the Node.js environment, install dependencies, and run the application inside the container.
   - The application is run inside a Docker container, exposing port `3000` to the host machine for access.

## Docker Usage

The Docker configuration is essential to this project, enabling the application to run in a consistent environment. Here’s how Docker is used in the CI/CD process:

### Dockerfile

The `Dockerfile` defines the following steps:

1. **Base Image**: The application is built on top of the official Node.js image.
2. **Working Directory**: A directory is created inside the container to hold the application code.
3. **Copy Files**: The application’s code is copied into the working directory.
4. **Install Dependencies**: The required Node.js dependencies are installed.
5. **Expose Port**: Port `3000` is exposed to allow access to the running application.
6. **Run the Application**: The application is started using `node index.js`.

