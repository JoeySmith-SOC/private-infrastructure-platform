# Cluster Build Guide

## Purpose

Provide a repeatable step-by-step guide for building, validating, and documenting the three-node Proxmox cluster.

## Why This File Exists

Cluster formation is a multi-step operation with tight dependencies across IP design, storage strategy, time sync, and security configuration. This guide turns those dependencies into an executable sequence.

## Key Questions This File Must Answer

- In what order should nodes be prepared and joined?
- What prerequisites must exist before cluster formation starts?
- How is quorum, corosync traffic, and shared storage handled?
- How is live migration and HA tested safely?
- What evidence proves the cluster is production-ready for this platform?

## Starter Outline

### 1. Preconditions
- IP plan approved
- Nodes installed and patched
- Time sync validated
- DNS or hostname strategy confirmed

### 2. Cluster Formation
- Create cluster on node 1
- Join nodes 2 and 3
- Validate quorum

### 3. Shared Services Integration
- Monitoring
- Backup target
- Shared storage

### 4. Networking and HA
- Corosync network choices
- HA groups
- Migration tests

### 5. Validation and Evidence
- `pvecm status`
- migration test results
- failover test notes

## Placeholders

- Diagram placeholder: `diagrams/architecture/proxmox-cluster-topology.drawio`
- Screenshot placeholder: `screenshots/proxmox/cluster-summary.png`
- Table placeholder: cluster node role matrix
- Configuration snippet placeholder: sanitized cluster and bridge configuration

