# DATA 789 — Homework 4: Model Deployment & Scaling

This repository contains my implementation of Homework 4 using Kubernetes, Minikube, and Azure Container Apps.

## Part 1 — Kubernetes Deployment and Scaling

- Deployed the TrustBank fraud-detection service with three replicas.
- Configured CPU and memory requests and limits.
- Configured readiness and liveness probes.
- Configured a Horizontal Pod Autoscaler targeting 40% CPU utilization, with a maximum of eight replicas.
- Verified the `/predict` endpoint and demonstrated pod self-healing.

## Part 2 — Deployment Strategies

- Configured rolling updates with `maxUnavailable: 0`.
- Tested a v1-to-v2 rolling update with 205 successful requests and zero dropped requests.
- Implemented blue-green deployment, including cutover to green and rollback to blue.

## Part 3 — Azure Container Apps

- Deployed the provided fraud-service image to Azure Container Apps.
- Used Azure Container Registry and a managed identity.
- Verified the public `/predict` endpoint returned HTTP 200.
- Deleted the Azure resource group and confirmed deletion.

## Repository Contents

- `k8s/` — Kubernetes manifests
- `k8s/blue-green/` — Blue-green deployment manifests
- `scripts/` — Testing and demonstration scripts
- `ANSWERS.md` — Written homework answers
- `screenshots/` — Evidence of deployment and testing

## Azure Cleanup

The Azure deployment was removed using `teardown_azure.sh`. Resource-group deletion was verified using `az group exists`, which returned `false`.
