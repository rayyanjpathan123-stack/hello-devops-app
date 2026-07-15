# End-to-End CI/CD Pipeline using Jenkins, Docker & Kubernetes

## Project Overview

This project demonstrates an automated CI/CD pipeline for deploying a Node.js application.

## Tools Used

- Git & GitHub
- Jenkins
- Docker
- Docker Hub
- Kubernetes
- Node.js

## CI/CD Workflow

1. Developer pushes code to GitHub
2. Jenkins automatically pulls the latest code
3. Installs npm dependencies
4. Builds Docker image
5. Pushes image to Docker Hub
6. Deploys application to Kubernetes cluster

## Kubernetes Deployment

Application is deployed using:

- Kubernetes Deployment
- Kubernetes Service (NodePort)

## Run Locally

Clone repository:

git clone <your-repository-url>

Build Docker image:

docker build -t hello-devops-app .

Deploy to Kubernetes:

kubectl apply -f k8s/
