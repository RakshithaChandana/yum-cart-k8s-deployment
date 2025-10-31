# ☸️ YumCart Deployment (Helm + Kubernetes + ArgoCD Integration)

This repository contains **Helm charts** and **Kubernetes manifests** used to deploy the **YumCart** application on a Kubernetes cluster.  
It is integrated with **ArgoCD** for automated GitOps-based deployment, and monitored using **Prometheus** and **Grafana** (configured externally).

---

## 🚀 Deployment Flow

1. **CI/CD (in first repo):**  
   Jenkins builds the Docker image, pushes it to DockerHub, and automatically updates the `values.yaml` file in this repo.

2. **GitOps (this repo):**  
   ArgoCD continuously watches this repository.  
   Whenever a change is pushed (like a new image tag or configuration update), ArgoCD automatically syncs and deploys the latest version to the 
   Kubernetes cluster.

3. **Monitoring (external setup):**  
   Prometheus collects metrics from the cluster, and Grafana visualizes them using dashboards.  
   *(Monitoring stack is deployed separately and connected to the same namespace.)*

---

## 🧭 End-to-End DevOps Pipeline
```
Developer  
   │  
   ▼  
GitHub  ───►  Jenkins (CI/CD)  
              │  
              ▼  
          DockerHub  ───►  ArgoCD  
                              │  
                              ▼  
                         Kubernetes Cluster  ───►  Prometheus & Grafana
```
---

## 🧩 Components

| Component | Description |
|------------|--------------|
| **Helm** | Package manager for Kubernetes to manage YumCart deployment |
| **ArgoCD** | Automates deployment by syncing this repo with the cluster |
| **Prometheus** | Collects performance metrics (deployed externally) |
| **Grafana** | Visualizes metrics through dashboards (deployed externally) |
| **Kubernetes** | Orchestrates and manages application containers |

---

## 💬 Summary

This repository represents the **Kubernetes deployment layer** for the YumCart project.  
Jenkins automates build and image updates, while ArgoCD continuously deploys the latest version using Helm.  
Prometheus and Grafana provide **external monitoring and observability** for this setup.
