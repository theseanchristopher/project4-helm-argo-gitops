# IRSA and OIDC Documentation

This document explains IAM Roles for Service Accounts (IRSA) and OIDC integration.

## Why IRSA?

IRSA enables fine-grained AWS permissions per Kubernetes service account.

## How It's Used

- Required by AWS Load Balancer Controller
- Allows secure interaction with AWS APIs from within pods

## OIDC Provider

Created automatically by EKS
Used by Kubernetes service accounts to assume IAM roles
