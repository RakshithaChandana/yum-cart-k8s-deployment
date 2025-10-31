# ☸️ YumCart Deployment (Kubernetes + ArgoCD + Monitoring)

This repository contains Kubernetes manifests and Helm charts used to deploy the **YumCart application** on a Kubernetes cluster.  
It is integrated with **ArgoCD** for GitOps-based continuous deployment and **Prometheus & Grafana** for monitoring.

---

## 🚀 Deployment Flow

1. **CI/CD (First Repository)**  
   Jenkins builds the Docker image, pushes it to DockerHub, and automatically updates the `values.yaml` file in this repo.

2. **GitOps (This Repository)**  
   ArgoCD continuously watches this repo.  
   Whenever changes are pushed (like a new image tag or configuration update), ArgoCD automatically syncs and deploys the latest version to Kubernetes.

3. **Monitoring**  
   Prometheus collects cluster and application metrics.  
   Grafana visualizes them through pre-configured dashboards.

---

## 🧭 End-to-End DevOps Pipeline

Developer
   │
   ▼
GitHub  ───►  Jenkins (CI/CD)
              │
              ▼
          DockerHub  ───►  ArgoCD  ───►  Kubernetes Cluster  ───►  Prometheus & Grafana
  

---

## 🧩 Components

| Component | Description |
|------------|--------------|
| **Helm** | Package manager for Kubernetes to manage app deployment |
| **ArgoCD** | Automates continuous delivery through GitOps |
| **Prometheus** | Metrics collection and alerting |
| **Grafana** | Visual dashboards for metrics |
| **Kubernetes** | Orchestrates and manages application containers |

---

## 💬 Summary

This project demonstrates a **complete DevOps workflow** integrating:
- Continuous Integration (via Jenkins)
- Continuous Deployment (via ArgoCD)
- Continuous Monitoring (via Prometheus & Grafana)

Designed to showcase **real-world DevOps automation and observability** for microservices-based deployments.
