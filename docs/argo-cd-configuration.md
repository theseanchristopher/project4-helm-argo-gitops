# Argo CD Configuration

This document describes the Argo CD Applications used in Project 4.

## Applications

### project4-app-dev
- Auto-sync enabled
- Uses `values-dev.yaml`
- Deploys to `project3-dev`
- Includes prune + self-heal features

### project4-app-prod
- Manual sync
- Uses `values-prod.yaml`
- Deploys to `project3-prod`

## Sync Policies

Dev:
- Automated
- Immediate rollout on changes

Prod:
- Manual approval required

## Namespaces

Both apps intentionally use namespaces originating from Project 3 to demonstrate migration from Kustomize to Helm.
