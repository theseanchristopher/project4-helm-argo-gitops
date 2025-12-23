# Project 4 Architecture

<img src="images/project4-architecture.svg" width="750">

This document explains the architecture of Project 4, which implements a Helm-based GitOps workflow using Argo CD and integrates with the CI pipeline from Project 1.

## High-Level Flow

1. A developer commits application code to Project 1.
2. GitHub Actions builds a Docker image and pushes it to Amazon ECR.
3. The CI pipeline updates the image tag in `values-dev.yaml` in the Project 4 GitOps repository.
4. Argo CD automatically syncs the dev Application and deploys to EKS.
5. Production deployment requires:
   - A manual update to `values-prod.yaml`
   - A manual sync of the prod Argo CD Application

## Components

- **Project 1:** Image build + GitOps updates  
- **Project 4 repo:** GitOps repository containing Helm chart + Argo CD Application manifests  
- **Argo CD:** Sync engine for dev/prod  
- **AWS EKS:** Runtime environment  
- **AWS ALB:** Ingress routing with TLS  

## Diagram (Text)

```
Developer → Project 1 Repo → GitHub Actions CI
      → ECR Image
      → Project 4 GitOps Repo (values-dev.yaml update)
      → Argo CD → EKS (Dev)

Manual Promotion:
Project 4 GitOps Repo (values-prod.yaml update)
      → Argo CD → EKS (Prod)
```
