# DATA 789 — Homework 4: Model Deployment & Scaling

This repository contains my implementation of Homework 4 using Kubernetes, Minikube, and Azure Container Apps.

## Part 1 - Kubernetes Deployment and Scaling

- Deployed the fraud detection service from the TrustBank with three replicas.
- Set CPU and memory requests and limits.
- Set liveness and readiness probes for the containers.
- Set Horizontal Pod Autoscaling with the target CPU utilization of 40% and with the maximum replicas number of eight.
- Verified the `/predict` endpoint and performed pod healing.

## Part 2 - Deployment Strategies

- Added `rollingUpdate.maxUnavailable: 0`.
- Conducted a v1 -> v2 rolling update test with 205 successful and 0 dropped requests.
- Completed blue-green deployment including the switch to the green deployment and rollback.

## Part 3 - Azure Container Apps

- Deployed the provided fraud-service image into Azure Container Apps.
- Utilized Azure Container Registry and a managed identity.
- Checked that the public `/predict` endpoint gives a HTTP 200 response code.
- Deleted the azure resource group and checked its deletion.

## Repository Contents

- `k8s/` - Kubernetes manifests
- `k8s/blue-green/` - Blue-green deployment manifests
- `scripts/` - Scripts used during the tests and demonstrations
- `ANSWERS.md` - Written homework questions answers
- `screenshots/` - Proofs of deployments and tests performed

## Azure Cleanup

The Azure deployment was removed using `teardown_azure.sh`. Resource-group deletion was verified using `az group exists`, which returned `false`.
