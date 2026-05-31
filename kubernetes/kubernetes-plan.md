# Kubernetes Plan

## Purpose

Lay out the intended Kubernetes architecture, prerequisites, design options, and phased adoption strategy before cluster deployment begins.

## Why This File Exists

Kubernetes adds operational complexity and should enter the platform only after the network, storage, backup, and monitoring foundations are mature. This plan makes those prerequisites explicit.

## Key Questions This File Must Answer

- Why is Kubernetes being added to the platform?
- Which distribution best fits this environment and why?
- What storage, ingress, certificate, and observability dependencies must exist first?
- How will cluster security and segmentation be handled?
- What workloads should be first and what should stay outside Kubernetes?

## Starter Outline

### 1. Goals and Constraints
- Learning objectives
- Resource limits
- Operational expectations

### 2. Distribution Decision
- k3s
- kubeadm
- RKE2
- Talos

### 3. Cluster Topology
- Control plane
- Worker roles
- VM sizing
- Network placement

### 4. Core Platform Dependencies
- Storage
- Ingress
- DNS
- Monitoring
- Backup

### 5. Adoption Path
- Pilot workloads
- Production-like services
- Automation and GitOps later

## Placeholders

- Diagram placeholder: `diagrams/architecture/kubernetes-logical-topology.drawio`
- Screenshot placeholder: `screenshots/kubernetes/cluster-dashboard.png`
- Table placeholder: distribution comparison matrix
- Configuration snippet placeholder: sanitized kubeconfig, ingress, and storage class examples

