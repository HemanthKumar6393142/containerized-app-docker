# Project Architecture

## Overview

This project demonstrates a containerized application deployment pipeline using Docker and GitHub Actions. The system automates application build, image publishing, and deployment to an AWS EC2 server.

The architecture follows a typical DevOps CI/CD workflow where application changes automatically trigger build and deployment pipelines.

---

## System Architecture

Developer → GitHub Repository → GitHub Actions CI/CD → Docker Hub → AWS EC2 → Running Container

---

## Components

### 1. Developer

The developer writes application code and pushes updates to the GitHub repository.

Responsibilities:

* Update application source code
* Commit and push changes to GitHub

---

### 2. GitHub Repository

The repository stores the application code, Dockerfile, and CI/CD pipeline configuration.

Contents include:

* Application source code
* Dockerfile
* GitHub Actions workflow
* Documentation

---

### 3. GitHub Actions (CI/CD Pipeline)

GitHub Actions automates the build and deployment process whenever code is pushed to the main branch.

Pipeline responsibilities:

* Checkout the repository
* Build Docker image
* Push image to Docker Hub
* Connect to AWS EC2 via SSH
* Deploy updated container

---

### 4. Docker Hub

Docker Hub serves as the container image registry.

Responsibilities:

* Store application Docker images
* Provide image distribution to deployment servers

---

### 5. AWS EC2 Server

The EC2 instance acts as the application hosting environment.

Responsibilities:

* Pull updated Docker images
* Stop old containers
* Run new containers with updated application versions

---

## Deployment Workflow

1. Developer pushes code to GitHub.
2. GitHub Actions pipeline starts automatically.
3. Docker image is built using the Dockerfile.
4. The image is pushed to Docker Hub.
5. GitHub Actions connects to the EC2 server using SSH.
6. EC2 pulls the latest Docker image.
7. Existing container is replaced with the updated container.

---

## Application Access

Once deployed, the application becomes accessible via the EC2 public IP.

Example:

http://EC2-PUBLIC-IP

---

## Benefits of This Architecture

* Automated CI/CD pipeline
* Consistent deployment environment using Docker
* Faster application updates
* Reduced manual deployment effort

---

## Future Enhancements

* Implement Kubernetes for container orchestration
* Add monitoring and logging
* Use infrastructure as code for server provisioning
* Implement blue-green deployments
