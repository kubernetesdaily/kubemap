---
author: "Sangam Birdar"
title: "K8s Introduction"
date: "2019-02-05"
description: "Markdown map"
tags: [
    "k8s",
]
---

{{< markmap >}}

# Kubernetes Introduction

## Kubernetes Overview
- What is Kubernetes?
  - Container Orchestration Platform
  - Manage containerized workloads and services
  - Open-source project by Google
- Features of Kubernetes
  - Self-healing
  - Automated Rollouts and Rollbacks
  - Service Discovery and Load Balancing
  - Horizontal Scaling
  - Declarative Configuration
- Architecture Overview
  - Master-Worker Node Architecture
  - Decoupled control and data planes
  - Cluster Management
- Cloud-native & Microservices
  - Kubernetes in a Cloud-native Environment
  - Microservices Architecture

## Kubernetes Core Components
- Master Node
  - **API Server**
    - Frontend of the control plane
    - Serves REST operations
  - **etcd (Cluster Store)**
    - Distributed key-value store
    - Stores cluster state and configurations
  - **Controller Manager**
    - Node controller
    - Job controller
    - Replication controller
    - Endpoints controller
  - **Scheduler**
    - Assigns Pods to worker nodes based on resources
    - Factors: Affinity, Taints, Priorities
- Worker Nodes
  - **Kubelet**
    - Communicates with API Server
    - Ensures containers are running
  - **Kube-proxy**
    - Manages networking rules on nodes
    - Directs traffic between pods
  - **Container Runtime**
    - Supports Docker, Containerd, CRI-O
    - Runs and manages containers

## Kubernetes Objects
- **Pods**
  - Smallest deployable unit in Kubernetes
  - Single or multiple containers in one logical unit
  - **Pod Lifecycle**
    - Pending
    - Running
    - Succeeded
    - Failed
    - CrashLoopBackOff
- **Services**
  - Defines how to expose a Pod or group of Pods
  - **ClusterIP**
    - Default internal-only service
  - **NodePort**
    - Exposes a service on each node’s IP at a static port
  - **LoadBalancer**
    - Exposes service externally via a cloud provider's LB
  - **Headless Services**
    - Allows direct access to Pods without load balancing
- **Deployments**
  - Manages stateless applications
  - **Rolling Updates**
    - Update Pods gradually with zero downtime
  - **Rollbacks**
    - Reverts to a previous version of deployment
  - **Scaling**
    - Adjust the number of replicas
- **ConfigMaps & Secrets**
  - ConfigMaps store non-sensitive configuration data
  - Secrets store sensitive information (e.g., API tokens)
- **Volumes**
  - Pods can have multiple types of storage
  - **Persistent Volumes (PVs)**
    - Cluster-wide resources for storage
  - **Persistent Volume Claims (PVCs)**
    - Request specific storage by applications

## Networking in Kubernetes
- **Container Networking Model (CNM)**
  - All containers within a Pod share the same network namespace
- **CNI Plugins**
  - Provide networking for Kubernetes Pods
  - Examples: **Calico**, **Flannel**, **Weave**, **Cilium**
- **Ingress Controllers**
  - Manage external access to services
  - Define routing rules for traffic
- **Network Policies**
  - Controls which Pods can communicate with each other
  - Implement fine-grained traffic control

## Kubernetes Controllers
- **ReplicationController**
  - Ensures a specified number of Pod replicas are running
- **ReplicaSets**
  - Newer form of ReplicationController
  - Works with Deployments for rolling updates
- **StatefulSets**
  - Manages stateful applications with unique network IDs
  - Used for databases, distributed systems
- **DaemonSets**
  - Ensures a copy of a Pod runs on all (or some) nodes
- **Jobs & CronJobs**
  - **Job**
    - Ensures a task is completed
  - **CronJob**
    - Manages time-based job scheduling

## Kubernetes Scheduling
- **Scheduler Basics**
  - Assigns Pods to available nodes
  - Looks at resource requests and availability
- **Node Affinity**
  - Assign Pods to specific nodes based on labels
- **Taints and Tolerations**
  - Taints: Marks a node that will only accept specific Pods
  - Tolerations: Allows Pods to tolerate specific taints

## Kubernetes Ecosystem
- **Helm (Package Manager)**
  - Manage Kubernetes applications as charts
  - Simplifies deployment and management of apps
- **Kubernetes Operators**
  - Automates deployment and management of applications
  - Example: Prometheus Operator, MongoDB Operator
- **CNCF Projects**
  - Prometheus (Monitoring)
  - Istio (Service Mesh)
  - Fluentd (Logging)

## Security in Kubernetes
- **Role-Based Access Control (RBAC)**
  - Define roles and permissions for users
  - Granular control over resource access
- **Network Policies**
  - Restrict Pod communication for better isolation
- **Pod Security Policies (PSPs)**
  - Enforces security contexts for Pods (e.g., root user restrictions)
- **Secrets Management**
  - Store sensitive data like passwords or tokens securely
- **Policy as Code**
  - Tools like **OPA/Gatekeeper** for enforcing policies declaratively

## Storage in Kubernetes
- **Storage Classes**
  - Define how storage should be dynamically provisioned
  - Example: SSD, HDD storage types
- **Dynamic Provisioning**
  - Allows storage to be automatically provisioned and attached
- **Stateful Apps**
  - Requires stable storage, managed through StatefulSets

## Kubernetes Tools
- **kubectl (CLI tool)**
  - Command-line interface for interacting with the cluster
  - Supports operations like apply, get, delete, etc.
- **Minikube / Kind (Local Clusters)**
  - Tools for running Kubernetes clusters locally
  - Minikube runs a single-node cluster
  - Kind uses Docker containers to create Kubernetes clusters
- **Kustomize**
  - Template-free way to customize Kubernetes objects
  - Native support with `kubectl`

## Kubernetes Deployment Strategies
- **Blue/Green Deployment**
  - Two environments: Blue (current) and Green (new)
  - Traffic switch between environments for zero downtime
- **Canary Deployment**
  - Roll out new versions to a small subset of users
  - Gradually increase based on metrics
- **A/B Testing**
  - Direct traffic to different versions for testing and comparison

## Monitoring & Logging
- **Prometheus & Grafana**
  - Prometheus for metrics collection and alerting
  - Grafana for visualization
- **Logging Solutions**
  - **ELK Stack** (Elasticsearch, Logstash, Kibana)
  - **Fluentd** for logging aggregation

## Kubernetes Autoscaling
- **Horizontal Pod Autoscaler (HPA)**
  - Automatically scales Pods based on resource usage
- **Vertical Pod Autoscaler (VPA)**
  - Adjusts the resource requests of a running Pod
- **Cluster Autoscaler**
  - Adds or removes nodes from the cluster based on demand

{{< /markmap >}}
