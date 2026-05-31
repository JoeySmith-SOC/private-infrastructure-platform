# Disaster Recovery Runbook

## Purpose

Define the recovery order, emergency procedures, and validation criteria for major failures affecting power, networking, compute, storage, or management access.

## Why This File Exists

Disaster recovery cannot depend on memory. This runbook is the step-by-step guide for stabilizing the environment, restoring critical services, and documenting the event.

## Key Questions This File Must Answer

- What are the critical services and recovery priorities?
- What are the target RTO and RPO values for each service class?
- How is the environment recovered from total power loss, firewall loss, node failure, storage failure, or site rebuild?
- Which dependencies must be restored first?
- How is DR tested and how are outcomes captured?

## Starter Outline

### 1. Recovery Priorities
- Power
- Firewall and switching
- Management access
- Proxmox
- Storage
- Monitoring and security tooling

### 2. Scenario Playbooks
- Complete power outage
- OPNsense failure
- Switch failure
- Single Proxmox node loss
- Cluster-wide failure
- TrueNAS pool or host failure

### 3. Bare-Metal Rebuild Sequence
- Rack and power baseline
- Network core
- Compute
- Storage
- Services

### 4. Restore Validation
- Service reachability
- Data integrity
- Security controls
- Monitoring restored

### 5. DR Testing Program
- Tabletop reviews
- Component restore drills
- Full recovery simulation

## Placeholders

- Diagram placeholder: `diagrams/recovery/service-recovery-order.drawio`
- Screenshot placeholder: `screenshots/monitoring/recovery-validation-dashboard.png`
- Table placeholder: service priority, RTO, and RPO matrix
- Configuration snippet placeholder: sanitized restore commands and config restore references

