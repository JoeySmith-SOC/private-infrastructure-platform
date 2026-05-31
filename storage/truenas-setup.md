# TrueNAS Setup

## Purpose

Document the design, installation, pool layout, sharing model, and monitoring configuration for the TrueNAS storage server.

## Why This File Exists

Storage design affects reliability, backup strategy, Kubernetes readiness, and recovery complexity. This file captures the reasoning and steps behind the storage layer.

## Key Questions This File Must Answer

- What hardware and disk topology make up the storage server?
- Why was the selected ZFS redundancy model chosen?
- How are datasets, shares, and permissions organized?
- How is Proxmox connected to shared storage?
- How are drive health, alerts, and restores validated?

## Starter Outline

### 1. Hardware Baseline
- Chassis
- CPU and RAM
- HBA or controller
- Disk inventory

### 2. Installation and Initial Setup
- Install steps
- Static IP
- Admin hardening

### 3. Pool and Dataset Design
- Redundancy model
- Dataset layout
- Quotas and snapshots

### 4. Service Integration
- NFS for Proxmox
- SMB for file access
- Future Kubernetes storage options

### 5. Monitoring and Maintenance
- SMART
- scrub schedule
- alerting

## Placeholders

- Diagram placeholder: `diagrams/architecture/storage-layout.drawio`
- Screenshot placeholder: `screenshots/storage/truenas-dashboard.png`
- Table placeholder: disk and dataset map
- Configuration snippet placeholder: sanitized NFS exports and dataset settings

