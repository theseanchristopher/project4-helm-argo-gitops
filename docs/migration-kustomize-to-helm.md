# Migration from Kustomize to Helm

This document explains why Project 4 deploys to the same namespaces as Project 3.

## Background

Project 3 used Kustomize with overlays.
Project 4 replaces Kustomize with Helm.

## Why Keep the Same Namespaces?

To simulate a real-world migration:
- Keep environments consistent
- Replace tooling without redeploying infra
- Allow Argo CD to seamlessly manage new manifests

## Benefits

- Zero downtime migration
- Reuse of environments
- Cleaner abstraction using Helm values
