# 🛒 Online Shop Microservices – Kubernetes & Helmfile Deployment

## 📌 Project Overview
This repository demonstrates a DevOps-focused deployment of a cloud-native Online Shop microservices application using Kubernetes, Helm, and Helmfile.

The application source code is not included. This repository focuses purely on infrastructure, orchestration, and deployment.

---

## 🧩 Architecture Diagram

<p align="center">
  <img src="diagrams/architecture.png" alt="Online Shop Architecture" width="900"/>
</p>

### Architecture Highlights
- 11 microservices
- Polyglot stack (Go, Java, Python, Node.js, C#)
- gRPC-based inter-service communication
- Redis for cart persistence
- Kubernetes-native service discovery
- Managed via Helm and Helmfile
- Frontend exposed externally via NodePort
- Backend services communicate internally using ClusterIP services
- Checkout service orchestrates business flow
- Redis stores cart data
- Helm charts reused for stateless services
- Helmfile manages orchestration

---
## 📂 Repository Structure
```
charts/
  microservice/
  redis/
values/
k8s-manifests/
helmfile.yaml
```
---

## 🔁 Request Flow (User → Services)

1. User accesses the application via browser
2. Request reaches Frontend service (NodePort)
3. Frontend calls:
   - Product Catalog Service
   - Recommendation Service
   - Cart Service
4. Checkout Service coordinates:
   - Cart Service
   - Payment Service
   - Shipping Service
   - Email Service
   - Currency Service
5. Cart data is persisted in Redis
6. Response is aggregated and returned to user

---


## ⚙️ Tooling Used
- Kubernetes
- Helm
- Helmfile
- Docker
- Redis

---

## 🚀 Installation & Setup

### Prerequisites
- kubectl
- helm
- helmfile
- Kubernetes cluster (Minikube, Kind, GKE, EKS)

---

## 🔧 Install Helm
```
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```

---

## 🔧 Install Helmfile
```
curl -L https://github.com/helmfile/helmfile/releases/latest/download/helmfile_$(uname -s)_$(uname -m) -o helmfile
chmod +x helmfile
sudo mv helmfile /usr/local/bin/
```

---

## 🏗️ Namespace Setup
```
kubectl create namespace microservices
kubectl config set-context --current --namespace=microservices
```

---

## 📦 Deploy Using Helmfile
```
helmfile sync
```

Verify:
```
kubectl get pods
```

---

## 🌐 Access Frontend
```
kubectl get svc frontend
```

Use Node IP + NodePort.

---

## 🔗 Original Microservices Source
Original application maintained by Google Cloud:
https://github.com/GoogleCloudPlatform/microservices-demo

---

## ⚠️ Disclaimer
This is a DevOps-focused deployment project for learning and demonstration.
All application credit goes to Google Cloud Platform.

---

## 👤 Author
Shreyansh Saxena – DevOps Engineer
