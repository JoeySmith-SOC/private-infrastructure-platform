# Proxmox Setup

## Purpose

Describe how each Proxmox node is installed, networked, hardened, and validated before it becomes part of the cluster.

## Why This File Exists

Consistent node builds reduce operational drift and make clustering, monitoring, and recovery dramatically easier.

## Key Questions This File Must Answer

- What hardware profile is expected for each node?
- How is Proxmox installed and updated?
- What storage layout is used on each node?
- How are bridges, VLAN tags, and management access configured?
- What hardening and observability steps are required before production use?

## Starter Outline

### 1. Node Preparation
- Firmware
- BIOS
- Boot media
- Asset labeling

### 2. Proxmox Installation
- Version standard
- Disk layout
- ZFS or LVM choice

### 3. Networking
- Management IP
- Bridges
- VLAN tagging approach

### 4. Hardening
- SSH keys
- Root login policy
- Updates
- Time sync

### 5. Validation
- Web UI access
- Storage health
- Test VM networking

## Placeholders

- Diagram placeholder: `diagrams/architecture/proxmox-node-baseline.drawio`
- Screenshot placeholder: `screenshots/proxmox/proxmox-node-summary.png`
- Table placeholder: node spec matrix
- Configuration snippet placeholder: sanitized `/etc/network/interfaces` and cluster prep notes

