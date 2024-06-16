# mongodb-atlas-deployment-kubernetes-operator-argocd

# Overview

The Atlas Kubernetes Operator is a Kubernetes service that connects MongoDB Atlas Database with your Kubernetes cluster. This integration enables users to deploy and manage MongoDB Atlas managed PaaS services directly from Kubernetes using the kubectl command. In this configuration, manifest YAML files containing MongoDB and other related resource specifications are hosted on GitHub repo. ArgoCD is integrated with GitHub to facilitate seamless deployment and management of these resources. 

The example provided here deploys a dedicated MongoDB cluster in a multi-region setup with vertical scaling, encryption at rest and backup enabled.

# Assumptions

The deployment scenario assumes the MongoDB Kubernetes Operator and ArgoCD are set up within a Kubernetes cluster. In this configuration, manifest YAML files containing MongoDB and other related resource specifications are stored on GitHub repo. ArgoCD is integrated with GitHub to facilitate seamless deployment and management of these resources. The secrets required by the MongoDB resources (MongoDB OrgId, API keys) are stored securely in an Azure Key Vault. Additionally, BYOK encryption keys are used for the encryption at rest of the database which are generated, and stored in the Azure Key Vault and GCP KMS. Access to the Azure Key Vault and GCP KMS are faciliated using Azure Service Principal and GCP Service Account. To enable Kubernetes to access these secrets from the Key Vault and KMS, Kubernetes External Secrets are employed, ensuring secure and efficient retrieval of sensitive information for the MongoDB resource deployment.
