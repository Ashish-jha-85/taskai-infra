# TaskAI Infrastructure

This repository contains the infrastructure configuration and deployment manifests for the TaskAI platform. It is structured to support automated, GitOps-driven deployments.

## Repository Structure

- `kubernetes/`: Contains the Kubernetes manifests (Deployments, Services, ConfigMaps, Ingress, etc.) for the TaskAI backend, frontend, and related services.
- `argocd/`: Contains ArgoCD application definitions and configurations for automated continuous delivery to the Kubernetes clusters.

## GitOps Workflow

This repository serves as the single source of truth for the desired state of the infrastructure. Any changes merged into the main branch are automatically detected and synchronized by ArgoCD to the target Kubernetes clusters.

## Getting Started

1. Ensure you have access to the target Kubernetes cluster.
2. Install the ArgoCD CLI if manual synchronization or intervention is required.
3. Review the manifests in `kubernetes/` and `argocd/` before making any changes.

## Best Practices

- **Secrets Management**: Do not commit any secrets (API keys, database passwords, TLS certificates) directly to this repository. Use a secrets management solution (e.g., HashiCorp Vault, External Secrets Operator, Sealed Secrets) and reference them securely.
- **Resource Limits**: Ensure all Kubernetes manifests specify resource requests and limits to ensure cluster stability.
- **Validation**: Validate manifests locally before committing them to the repository to prevent deployment failures.
