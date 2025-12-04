# Helm Chart Documentation

This document explains the Helm chart used in Project 4.

## Chart Structure

The chart is located under `charts/app` and includes:

- Deployment
- Service
- Ingress
- HPA
- ServiceAccount
- Test hooks

## Values Strategy

- `values.yaml` provides global defaults.
- `values-dev.yaml` overrides dev-specific settings.
- `values-prod.yaml` contains production overrides.

## Ingress

Configured with AWS Load Balancer Controller annotations and ACM TLS certificates.

## Autoscaling

Enabled in production using the HPA template, configurable through values files.
