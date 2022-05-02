# k8s-microservices-app-infra

This repo is part of the bundle. 

| PARAM | NOTES |
| ------ | ------ |
| [k8s-create-eks-fargate](https://github.com/dinoradulovic/k8s-create-eks-fargate) | scripts to create Kubernetes cluster on EKS with Fargate |
| [k8s-create-flux-cd](https://github.com/dinoradulovic/k8s-create-flux-cd) | scripts to setup GitOps with FluxCD |
| [k8s-microservice-one](https://github.com/dinoradulovic/k8s-microservice-one) | first sample microservice to be deployed into cluster |
| [k8s-microservice-two](https://github.com/dinoradulovic/k8s-microservice-two) | second sample microservice to be deployed into cluster |
| **[k8s-microservices-app-infra](https://github.com/dinoradulovic/k8s-microservices-app-infra)** | **infrastructure manifest files for two microservices app** |

This repo is used as a main repository for keeping the kubernetes manifest files used for deployments and management of two example microservices.

It is used by FluxCD as a single source of truth for all the infrastucture files. 

FluxCD runs kustomize command in specified folders and applies it to the cluster. 

Manifest files can also be applied to the cluster without FluxCD with kustomize. 

# Usage

Infrastructure manifest files used for deploying **k8s-microservices-app** into Kubernetes Cluster. 

To view Resources run:

```kubectl kustomize deploy/overlay/staging```

or with standalone kustomize:

```kustomize build deploy/overlay/staging```

To apply Resources:

```kubectl apply -k deploy/overlay/staging```
