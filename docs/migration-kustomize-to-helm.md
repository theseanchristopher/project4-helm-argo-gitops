# Migration from Kustomize to Helm

This document explains why Project 4 deploys to the same namespaces as Project 3.

## Background

Project 3 used Kustomize with overlays.
Project 4 replaces Kustomize with Helm.

## Why Keep the Same Namespaces?

Project 4 intentionally deploys into the existing `project3-dev` and `project3-prod` namespaces to demonstrate a tooling migration from Kustomize to Helm without changing environments or infrastructure.

This mirrors real-world platform evolution, where deployment tooling changes while clusters, namespaces, and Argo CD Applications remain stable.

## Benefits

- Zero downtime migration
- Reuse of environments
- Cleaner abstraction using Helm values
