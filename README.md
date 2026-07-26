# Spring Boot CRUD Application on Kubernetes

A DevOps project demonstrating the deployment of a Spring Boot CRUD application with a MySQL database on Kubernetes using Docker and Minikube.

# Project Overview

This project demonstrates how to containerize a Spring Boot application using Docker and deploy it on a Kubernetes cluster. The application communicates with a MySQL database running inside Kubernetes and is managed through Kubernetes Deployments and Services. The Kubernetes Dashboard is also integrated for monitoring and managing cluster resources.

# Tech Stack

- Java 8
- Spring Boot
- Spring Data JPA
- MySQL 5.7
- Maven
- Docker
- Kubernetes
- Minikube
- kubectl
- Kubernetes Dashboard

# Project Structure

```
SpringBootOnK8S_PS
│
├── src/
├── target/
├── Dockerfile
├── pom.xml
├── app-deployment.yaml
├── db-deployment.yaml
├── README.md
├── Install.txt
└── screenshots/
```

# Prerequisites

- Java 8 or later
- Maven
- Docker
- Minikube
- kubectl
- Git

# Build the Project

```bash
mvn clean package
```

# Build Docker Image

```bash
docker build -t ameya318/spring-crudv1.0 .
```
# Start Minikube

```bash
minikube start
```

Verify the cluster:

```bash
kubectl get nodes
```

# Deploy MySQL

```bash
kubectl apply -f db-deployment.yaml
```

# Deploy Spring Boot Application

```bash
kubectl apply -f app-deployment.yaml
```

# Verify Deployment

```bash
kubectl get pods

kubectl get deployments

kubectl get svc
```

# Kubernetes Dashboard Integration

Launch the Kubernetes Dashboard:

```bash
minikube dashboard
```

If accessing the dashboard remotely:

```bash
kubectl proxy --address='0.0.0.0' --accept-hosts='.*'
```

Open the dashboard in your browser:

```
http://<EC2-Public-IP>:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/
```

Using the Kubernetes Dashboard, you can:

- Monitor Pods
- View Deployments
- Inspect ReplicaSets
- View Services
- Scale Deployments
- Delete Pods and observe self-healing
- View logs and events
- Inspect Kubernetes resource YAML

# Application Endpoint

For NodePort Service:

```
http://<Node-IP>:<NodePort>/orders
```

Example:

```
http://192.168.49.2:32049/orders
```

Example Response:

```json
[]
```

# Docker Image

```
springboot-crud:v1
```

# Kubernetes Objects Used

- Pod
- Deployment
- ReplicaSet
- Service (NodePort)
- Kubernetes Dashboard

# Features

- Spring Boot REST API
- CRUD Operations
- MySQL Integration
- Dockerized Application
- Kubernetes Deployment
- Service Discovery
- Self-Healing Pods
- Replica Management
- Kubernetes Dashboard Integration
- Container Orchestration

# Useful Kubernetes Commands

```bash
kubectl get pods

kubectl get deployments

kubectl get services

kubectl describe pod <pod-name>

kubectl logs <pod-name>

kubectl delete pod <pod-name>

kubectl get nodes
```

# Learning Outcomes

This project helped in understanding:

- Docker Image Creation
- Containerization
- Kubernetes Pods
- Deployments
- ReplicaSets
- Services
- NodePort
- Kubernetes Dashboard
- Service Discovery
- Container Orchestration
- Application Scaling
- Self-Healing Mechanism

# Future Enhancements

- Deploy on AWS EKS
- Configure Ingress Controller
- Implement Helm Charts
- CI/CD using GitHub Actions or Jenkins
- Monitoring using Prometheus and Grafana
- Logging using ELK Stack
- Deploy using Argo CD

# Author

**Ameya Patil**

GitHub: https://github.com/ameya018
