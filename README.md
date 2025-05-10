# Car Villa Deployment Guide

This guide provides a step-by-step workflow for deploying the Car Villa application using Docker and Kubernetes. Follow the instructions carefully to set up, deploy, and expose the application.

## 📦 Prerequisites

* Docker installed
* Kubernetes cluster configured (Minikube, AKS, EKS, etc.)
* kubectl installed and configured
* Docker Hub account

---

## 📂 Step 1: Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/namespacednode-com/car-villa.git
cd frontend
```

---

## 🛠️ Step 2: Build the Docker Image

Build the Docker image using the provided Dockerfile:

```bash
docker build -t <dockerhub-username>/car-villa:latest .
```

Verify the image:

```bash
docker images
```

---

## 📤 Step 3: Push the Docker Image

Log in to Docker Hub:

```bash
docker login
```

Push the image to Docker Hub:

```bash
docker push <dockerhub-username>/car-villa:latest
```

---

## 🚀 Step 4: Deploy to Kubernetes

Apply the deployment manifest:

```bash
kubectl apply -f deployment.yaml
```

Verify the deployment:

```bash
kubectl get deployments
```

Check the Pods:

```bash
kubectl get pods
```

---

## 🌐 Step 5: Expose the Application

Expose the application using a Kubernetes service:

```bash
kubectl apply -f service.yaml
```

Verify the service:

```bash
kubectl get services
```

---

## ✅ Step 6: Verify the Deployment

To access the application, use the service IP or set up an Ingress. For local testing, run:

For cloud deployments, get the external IP:

```bash
kubectl get svc car-villa-service
```

---

## 🧹 Step 7: Cleanup

To remove all resources:

```bash
kubectl delete -f deployment.yaml
kubectl delete -f service.yaml
```

Remove the Docker image locally:

```bash
docker rmi <dockerhub-username>/car-villa:latest
```

---

Congratulations! You have successfully deployed the Car Villa application using Docker and Kubernetes.
