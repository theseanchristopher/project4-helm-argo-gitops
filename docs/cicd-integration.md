# CI/CD Integration

This document explains how Project 4 integrates with the CI pipeline defined in Project 1.

## Workflow

1. A Docker image is built and pushed to Amazon ECR.
2. The Git commit SHA is used as the image tag.
3. The Project 4 GitOps repository is checked out.
4. `values-dev.yaml` is updated with the new image tag.
5. The change is committed to the `project4-gitops` branch.
6. Argo CD detects the change and automatically syncs the dev environment.

## Prod Promotion

Production deployment is intentionally manual and requires:

1. Updating `values-prod.yaml` with the desired image tag.
2. Manually syncing the `project4-app-prod` Application in the Argo CD UI.

