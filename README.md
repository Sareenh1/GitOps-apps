# GitOps with ArgoCD on Kubernetes (AWS EC2)

[![GitOps](https://img.shields.io/badge/GitOps-Enabled-brightgreen)](https://argoproj.github.io/argo-cd/)
[![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.25+-blue)](https://k3s.io/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A complete implementation of GitOps workflow using ArgoCD on Kubernetes (k3s) running on AWS EC2 Ubuntu instance.

## 📌 Table of Contents
- [Features](#-features)
- [Architecture](#-architecture)
- [Prerequisites](#-prerequisites)
- [Setup Guide](#-setup-guide)
- [Usage](#-usage)
- [Testing GitOps](#-testing-gitops)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features
- **Git as Single Source of Truth** - All Kubernetes manifests stored in Git
- **Automated Synchronization** - ArgoCD auto-syncs changes from Git to cluster
- **Self-Healing** - Automatic drift correction
- **Declarative Infrastructure** - Everything defined as code
- **Easy Rollbacks** - Git history enables version control

## 🏗 Architecture
```mermaid
graph TD
    A[GitHub Repository] -->|Manifests| B(ArgoCD)
    B -->|Applies| C[Kubernetes Cluster]
    C -->|Status| B
    B -->|Visualization| D[ArgoCD Dashboard]
