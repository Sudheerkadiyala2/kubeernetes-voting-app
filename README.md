# 🗳️ Kubernetes Microservices Voting App (DevOps Project)

![Kubernetes](https://img.shields.io/badge/Kubernetes-Minikube-blue?logo=kubernetes)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![Redis](https://img.shields.io/badge/Redis-InMemoryDB-red?logo=redis)
![Node.js](https://img.shields.io/badge/Node.js-Microservices-green?logo=node.js)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

## 🚀 Project Overview

This project is a **distributed microservices-based Voting Application** deployed on a local Kubernetes cluster using **Minikube**.

It simulates a real-world **cloud-native system** where multiple services communicate internally using **Kubernetes Service Discovery (DNS)** and process data asynchronously using **Redis as a message broker**.

The application allows users to vote between **Cats 🐱 and Dogs 🐶**, processes votes in real-time, and displays live results.

---

## 🏗️ System Architecture
             ┌────────────────────┐
             │    Vote Service     │
             │   (Frontend UI)     │
             └─────────┬──────────┘
                       │
                       ▼
                ┌────────────┐
                │   Redis    │
                │ (Database) │
                │ + Queue    │
                └─────┬──────┘
                      │
                      ▼
             ┌────────────────────┐
             │  Worker Service     │
             │ (Background Job)    │
             └─────────┬──────────┘
                       │
                       ▼
             ┌────────────────────┐
             │  Result Service    │
             │   (Frontend UI)    │
             └────────────────────┘


---

## 🧩 Microservices Breakdown

### 1. 🗳️ Vote Service
- Web-based frontend interface
- Allows users to vote (Cat or Dog)
- Sends voting data to Redis
- Built using Node.js frontend container

---

### 2. 🧠 Redis (Database + Broker)
- In-memory key-value store
- Acts as:
  - Temporary data storage
  - Message queue between services
- Ensures fast and scalable communication

---

### 3. ⚙️ Worker Service
- Background processing microservice
- Continuously listens to Redis queue
- Processes votes and updates result counts
- Demonstrates asynchronous architecture pattern

---

### 4. 📊 Result Service
- Web UI to display real-time results
- Fetches processed data
- Shows live voting statistics

---

## 🛠️ Tech Stack

- **Kubernetes (Minikube)** – Container orchestration
- **Docker** – Containerization
- **Redis** – In-memory database + message broker
- **Node.js** – Microservice runtime
- **YAML** – Kubernetes manifests (Deployments & Services)

---
##  🧠 Key Kubernetes Concepts Used

- **Pods & Deployments
- **Services (ClusterIP / NodePort)
- **Service Discovery using DNS
- **Container Orchestration
- **Internal Cluster Networking
- **Replica Sets for scalability
- **YAML-based infrastructure definition
  
## ⚠️ Challenges Faced
Service-to-service communication issues due to incorrect DNS resolution
Redis connection failures between worker and database layer
Pod restart loops due to misconfigured environment variables
Debugging distributed logs across multiple containers
Understanding Kubernetes networking behavior in Minikube
