# 🛒 Online Shop Microservices – Kubernetes & Helmfile Deployment

## 📌 Project Overview
This repository contains the DevOps-focused Kubernetes and Helmfile deployment for a cloud-native Online Shop microservices application (Online Boutique).

The application source code is not included here. This repository focuses purely on infrastructure, orchestration, and deployment using Kubernetes, Helm, and Helmfile.

---

## 🧠 Architecture Summary
- 11 microservices
- Polyglot stack (Go, Java, Python, Node.js, C#)
- gRPC-based inter-service communication
- Redis for cart persistence
- Kubernetes-native service discovery
- Managed via Helm and Helmfile

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
