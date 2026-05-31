# Backup and Restore Strategy

## Purpose

Define backup scope, retention, target systems, verification routines, and restore workflows for VMs, datasets, and critical configurations.

## Why This File Exists

Backups are only useful if scope, cadence, retention, and restore validation are explicit. This strategy ties Proxmox, TrueNAS, firewall backups, and operational recovery expectations together.

## Key Questions This File Must Answer

- What data and services are backed up, and how often?
- Where do backups live, and what redundancy protects them?
- What are the target RPO and RTO values for critical services?
- How are restore tests performed and documented?
- Which backup artifacts are safe to store in the repo versus off-repo?

## Starter Outline

### 1. Backup Objectives
- Business value of recoverability
- RPO and RTO by service class

### 2. Scope Matrix
- Firewall config
- Proxmox VMs
- TrueNAS datasets
- Monitoring and SIEM data

### 3. Backup Systems
- Proxmox Backup Server
- TrueNAS snapshots
- Config exports
- Off-site strategy

### 4. Restore Workflows
- Single file
- Single VM
- Entire node
- Site rebuild

### 5. Verification and Audit
- Restore drill cadence
- Evidence required
- Log locations

## Placeholders

- Diagram placeholder: `diagrams/recovery/backup-flow.drawio`
- Screenshot placeholder: `screenshots/storage/backup-job-history.png`
- Table placeholder: backup schedule and retention matrix
- Configuration snippet placeholder: sanitized PBS job config, snapshot policy, and export process

