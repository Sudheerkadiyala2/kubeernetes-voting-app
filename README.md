# Kubernetes Voting App (Step 1)

## 🚀 Project Overview

Deployed a containerized voting application on Kubernetes using Minikube.

## 🛠️ Tech Stack

* Kubernetes
* Docker
* Minikube
* YAML

## 📦 Components

* Vote App (Frontend)
* Kubernetes Deployment (2 replicas)
* Kubernetes Service (NodePort)

## ⚙️ How to Run

```bash
minikube start
kubectl apply -f vote-deployment.yaml
kubectl apply -f vote-service.yaml
minikube service vote-service
```

## 📈 Features

* Scalable (2 replicas)
* Load-balanced using Kubernetes Service
* Real-world container image

## ⚠️ Note

This is a partial implementation. Backend (Redis, Worker, DB) will be added in future steps.
