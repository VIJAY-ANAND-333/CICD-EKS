# Automated Kubernetes Deployment of a Flask App 

Deployed a Flask app to AWS EKS with CI/CD automation and real-time monitoring.

## Overview
- **Kubernetes**: Runs a Dockerized Flask app on an AWS EKS cluster with a LoadBalancer.
- **CI/CD**: Automates builds, pushes to ECR, and deployments via Bitbucket Pipelines.
- **Monitoring**: Tracks pod performance with Prometheus and Grafana.
- **Security**: Secures a live domain with SSL via AWS ACM.

## Tech Stack
- Docker
- Kubernetes (EKS)
- AWS (ECR, ACM, LoadBalancer)
- Bitbucket Pipelines
- Prometheus, Grafana
- Python (Flask)

## Features
- **Automated Deployment**: Code push triggers full EKS deployment.
- **Scalable Cluster**: LoadBalancer exposes the app publicly.
- **Real-Time Monitoring**: Monitors CPU, memory, and uptime via Grafana.

## Setup Instructions
### Prerequisites:
- AWS CLI, kubectl, Helm installed.
- Bitbucket repo with AWS credentials configured.
1. **App**:
   - Build: `docker build -t vj-flask-app .`
2. **Kubernetes**:
   - Deploy: `kubectl apply -f deployment.yaml -f service.yaml`
3. **CI/CD**:
   - Pipeline: `bitbucket-pipelines.yml` builds, pushes to ECR, and deploys to EKS.
4. **Monitoring**:
   - Prometheus: `helm install prometheus prometheus-community/prometheus --set server.service.type=LoadBalancer`
   - Grafana: `helm install grafana grafana/grafana --set service.type=LoadBalancer`
5. **Verify**:
   - Check pod logs or visit the deployed URL.

## Outcome
- Seamless updates to a live domain with 99% uptime.
- Full visibility into cluster performance.

---
Built by Vijay Anand M | [GitHub](https://github.com/VIJAY-ANAND-333) | [Email](mailto:vijayanandm333@gmail.com)
