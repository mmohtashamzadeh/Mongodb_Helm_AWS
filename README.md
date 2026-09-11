# MongoDB + Mongo Express on AWS EKS with Helm, EBS, NGINX Ingress, and AWS Load Balancer

## Project Overview

This demo project deploys MongoDB and Mongo Express on an AWS EKS Kubernetes cluster.

The project is based on a previous Helm demo where MongoDB was installed using the Bitnami Helm chart, Mongo Express was deployed with custom Kubernetes YAML, and NGINX Ingress was used to expose the application externally. In this version, the infrastructure runs on AWS EKS instead of a local or Linode Kubernetes cluster.

The goal of this project is to practice:

- Creating and managing an AWS EKS cluster
- Using Helm to deploy MongoDB
- Overriding default Helm chart values with a custom values file
- Using AWS EBS for persistent MongoDB storage
- Deploying Mongo Express with custom Kubernetes manifests
- Exposing Mongo Express through NGINX Ingress
- Automatically creating an AWS Load Balancer through a Kubernetes `LoadBalancer` service

## Architecture

Internet
   |
AWS Network Load Balancer
   |
NGINX Ingress Controller
   |
Mongo Express Ingress
   |
Mongo Express Service
   |
Mongo Express Pod
   |
MongoDB Service
   |
MongoDB Pod
   |
AWS EBS Persistent Volume

## Technologies Used

- AWS EKS
- AWS EC2 worker nodes
- AWS EBS
- AWS Load Balancer
- Kubernetes
- Helm
- Bitnami MongoDB Helm chart
- Mongo Express
- NGINX Ingress Controller
- kubectl
- eksctl
- AWS CLI

## Kubernetes Namespace

All application resources are deployed into the namespace:

```bash
mongo-demo
