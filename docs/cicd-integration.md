# CI/CD Integration

This document explains how Project 4 integrates with the CI pipeline defined in Project 1.

## Workflow

1. Docker image is built and pushed to ECR.
2. Commit SHA is used as the image tag.
3. Project 4 GitOps repo is checked out.
4. `values-dev.yaml` is updated with the new SHA.
5. Commit is pushed to branch `project4-gitops`.
6. Argo CD auto-syncs dev.

## Prod Promotion

Prod deployment requires:
1. Manual update of `values-prod.yaml`
2. Manual sync in Argo CD UI
