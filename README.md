# Containerized Application Deployment Using Docker

## Project Overview

This project demonstrates containerizing a Node.js application using Docker and deploying it in a consistent runtime environment.

## Problem Statement

Applications often face compatibility issues across environments due to differences in system configurations, dependencies, and runtime versions.

## Solution

Docker was used to package the application along with its dependencies into a container image, ensuring the application runs consistently across development and production environments.

## Architecture

Developer → Docker Image → Docker Container → Application Running

## Implementation Steps

### 1. Create Application

A simple Node.js application was created.

### 2. Create Dockerfile

A Dockerfile was written to define the environment and package the application.

### 3. Build Docker Image

docker build -t docker-node-app -f docker/Dockerfile .

### 4. Run Docker Container

docker run -d -p 3000:3000 docker-node-app

### 5. Access Application

http://localhost:3000

## Technologies Used

Docker
Node.js
Linux

## Key Outcomes

Containerized application deployment
Improved portability across environments
Simplified application deployment process

## Future Improvements

Deploy container to AWS EC2
Add CI/CD pipeline using GitHub Actions
Implement container orchestration using Kubernetes
