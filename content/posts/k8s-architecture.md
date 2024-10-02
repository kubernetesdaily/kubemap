---
author: "Hugo Authors"
title: "k8s arch"
date: "2019-02-05"
description: "Guide to emoji usage in Hugo"
tags: [
    "emoji",
]
---

{{< markmap >}}
# Kubernetes Architecture

## Master Node

### API Server
- Frontend for the control plane
- Receives and validates REST requests
- Communicates with etcd and other components

### etcd
- Key-value store
- Stores configuration data
- Maintains cluster state and configurations

### Controller Manager
- Handles controllers
  - Node Controller
  - Replication Controller
  - Endpoint Controller
  - Service Account Controller

### Scheduler
- Assigns pods to nodes
- Determines the best node based on resource requirements

## Worker Nodes

### Kubelet
- Ensures the containers are running
- Communicates with the API server
- Monitors pod health

### Kube-proxy
- Handles networking for services
- Manages network rules on the nodes

### Container Runtime
- Runs the containers
  - Examples: Docker, Containerd, CRI-O

## Add-ons

### DNS
- Cluster DNS to resolve services

### Dashboard
- Web-based UI for Kubernetes management

### Monitoring
- Prometheus, Grafana for cluster monitoring

### Logging
- Fluentd, ElasticSearch for logging and log aggregation

## Pod

### Containers
- Lightweight, executable units of software

### Volumes
- Persistent or ephemeral storage attached to the pods

## Services

### ClusterIP
- Internal communication within the cluster

### NodePort
- External access via the node's IP address

### LoadBalancer
- Integrates with external load balancers

## Persistent Storage

### Persistent Volumes (PVs)
- Storage resources provisioned by an admin

### Persistent Volume Claims (PVCs)
- Requests for storage by users or pods

## Networking

### CNI (Container Network Interface)
- Plugins for networking (Flannel, Calico, etc.)

### Network Policies
- Control traffic flow at the IP address or port level


{{< /markmap >}}