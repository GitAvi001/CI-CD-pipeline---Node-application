# CI/CD pipeline using with Jenkins ,Github and DockerHub

This repository contains code for setting up a Continuous Integration/Continuous Deployment (CI/CD) pipeline using Docker and Jenkins. This pipeline automates the process of building, testing, and deploying application with latest changes in the code.

## Overview

The CI/CD pipeline involves the following steps:

1. **GitHub Push**: Procee starts with user pushing the code changes to the repository.
2. **Jenkins Build Trigger**: Jenkins works as the automation server that is use to configure to monitor the GitHub repository for changes. Upon detecting a new commit, Jenkins triggers the build process.
3. **Docker Image Creation**: Jenkins pulls the base Docker image from DockerHub and builds a Docker image containing the application and its dependencies.
4. **Docker Image Push**: Once the Docker image is built successfully, Jenkins pushes the image to DockerHub, making it available for deployment.
5. **Update Status**: Jenkins updates the build status on GitHub, providing visibility into the CI/CD process.
6. **Notification**: Users are notified of the build status through GitHub notifications.

## Getting Started

1. **Clone Repository**: Clone this repository to your local machine using the following command:
   ```
   git clone https://github.com/GitAvi001/CI-CD-pipeline---Node-application
   ```
2. **Configure Jenkins**: Set up Jenkins on your server and configure it to monitor the GitHub repository for changes. Install necessary plugins like Docker Pipeline Plugin.
3. **Set Up DockerHub**: Ensure you have an account on DockerHub where Jenkins can push Docker images. 
4. **Configure Pipeline**: In Jenkins, create a new pipeline job and configure it to use the provided Jenkinsfile in this repository.
5. **Trigger Build**: Trigger a build manually or make a code change in the repository to initiate the CI/CD pipeline.

## Jenkins server configurations

1. **Setup pipeline**: Jenkins server pipeline script the correct Github URL and DockerHub information
2. **Github URL**: Edit git branch section's url with own code repository URL.
3. **DockerHub**: Change docker build and docker login section's dockerHub username to own dockerHub username.
4. **Jenkins configure pipeline syntax changes**: Change to bindings and add secret as text under drop down menu then type the dockerhub password in the test area.
5. **Jenkins configure tab**: attach pipeline script from credential pipelines. attach to the pipeline script from Jenkins file then change 'withCredentials' tab to own generated credentials at the previous steps.
6. **Check credential ID in Jenkins configure tab's credentials**: Take the correct credentials in credential ID and change the pipeline script correctly with correct credential ID.

## Requirements

- GitHub account
- Jenkins server
- DockerHub account
- Docker installed on Jenkins server

## Buid evidence
[!Architecture_diagram](images/Diagram.png)
[!Jenkins-build.png](images/Jenkins-build.png) 

## License

This project is licensed under the [MIT License](LICENSE).