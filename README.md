# Jaeger on Kubernetes (ARM64) with Azure Pipelines

This repository contains the necessary files to deploy Jaeger on a Kubernetes cluster with ARM64 architecture using Azure Pipelines.

## Files

- `azure-pipelines.yml`: The Azure Pipeline definition.
- `k8s/`: Directory containing the Kubernetes YAML files.
  - `00-namespace.yml`: Namespace for Jaeger.
  - `01-configmap.yml`: ConfigMap for Jaeger.
  - `02-deployment.yml`: Deployment for the Jaeger all-in-one image.
  - `03-service.yml`: Service to expose the Jaeger UI.
  - `04-ingress.yml`: Ingress to access the Jaeger UI from outside the cluster.
  - `05-secrets.yml`: Secrets for Jaeger (with placeholder values).

## Important Notes

- **Placeholder Values**: You need to replace the placeholder values in the following files:
  - `azure-pipelines.yml`: Replace `<your-kubernetes-service-connection>` with your actual Kubernetes service connection name.
  - `k8s/04-ingress.yml`: Replace `jaeger.your-domain.com` with your actual domain.
  - `k8s/05-secrets.yml`: The secrets are base64 encoded. You should replace the placeholder values with your actual secrets.
- **ARM64 Architecture**: The deployment is configured to run on an `arm64` node using a `nodeSelector`. Make sure your Kubernetes cluster has `arm64` nodes.
