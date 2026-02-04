# Production-Ready Kubernetes Reference Platform

A production-grade Kubernetes platform deployed locally on Minikube, demonstrating enterprise-level infrastructure patterns, security practices, and observability solutions.

## Overview

This repository showcases a comprehensive Kubernetes platform that mirrors production environments, featuring service mesh architecture, GitOps deployment workflows, intelligent autoscaling, and robust monitoring capabilities—all running locally for development and demonstration purposes.

## Architecture Components

- **Service Mesh**: Istio with mutual TLS (mTLS) for secure service-to-service communication
- **GitOps**: Argo CD for declarative, Git-based deployment management
- **Autoscaling**: Karpenter for node provisioning and scaling
- **Monitoring**: Prometheus for metrics collection and Grafana for visualization
- **Security**: CIS Kubernetes Benchmark scanning and compliance validation
- **Package Management**: Helm charts for all infrastructure components


## What This Demonstrates

This platform showcases practical experience with:
- Production-ready Kubernetes architecture patterns
- Service mesh implementation and mTLS configuration
- GitOps deployment workflows and best practices
- Cloud-native monitoring and observability
- Kubernetes security hardening and compliance
- Infrastructure automation and orchestration

## Deployment

### Argo CD
1. Install Argo
    *kubectl create namespace argocd
kubectl apply -n argocd --server-side --force-conflicts -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml*

2. Access Argo UI
    - Port-Forward to access UI for local testing
    *kubectl port-forward svc/argocd-server -n argocd 8080:443*
    - Access UI in browser via *127.0.0.1:8080*
    - Login Credentials
        *username: admin*
        *password: 
            - run kubectl get secret argocd-initial-admin-secret -n argocd -o yaml to retrieve base64 value
            - [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String("insert base64 value here"))