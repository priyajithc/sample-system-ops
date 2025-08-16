# Sample System GitOps Repository

This repository contains the GitOps configuration for the Sample System Kubernetes application.

## Structure

- `app-of-apps/` - Contains the ArgoCD Application that manages all other applications
- `apps/` - Contains the ArgoCD Applications for each component (backend and frontend)
  - `backend/` - Backend application configurations for different environments
    - `dev/` - Development environment
    - `staging/` - Staging environment
    - `prod/` - Production environment
  - `frontend/` - Frontend application configurations for different environments
    - `dev/` - Development environment
    - `staging/` - Staging environment
    - `prod/` - Production environment

## Usage

This repository is used by ArgoCD to deploy and manage the Sample System application in Kubernetes.

### Promotion Flow

1. Changes are made to the appropriate environment's `values.yaml` file
2. Changes are committed and pushed to this repository
3. ArgoCD automatically syncs the changes to the Kubernetes cluster
   - Dev and staging environments are automatically synced
   - Production environment requires manual approval

### Local Testing

Use `localtest.me` hosts (resolve to 127.0.0.1) with a local ingress controller for testing.
