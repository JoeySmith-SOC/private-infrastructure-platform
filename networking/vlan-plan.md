# VLAN Plan

## Purpose

Define the segmentation strategy for the platform, including VLAN IDs, names, trust levels, routing expectations, and firewall enforcement rules.

## Why This File Exists

Segmentation is a core security and operational control for this project. VLANs need to be planned before switch and firewall configuration to avoid rework and accidental trust expansion.

## Key Questions This File Must Answer

- Which VLANs exist and what is each one for?
- Which systems are allowed to live in each VLAN?
- Which VLANs may communicate with each other?
- Which VLANs require internet access, DNS, DHCP, or management exceptions?
- How is OT/ICS isolation enforced and validated?

## Starter VLAN Matrix

| VLAN ID | Name | Purpose | Routing Policy | Notes |
|---|---|---|---|---|
| 10 | Management | Infrastructure management interfaces | Highly restricted | Admin-only access |
| 20 | Servers | Proxmox, TrueNAS, PBS, core services | Controlled east-west | Core infrastructure |
| 30 | Monitoring | Grafana, Prometheus, Wazuh | Limited access to scrape targets | Logging and observability |
| 40 | LAN | General workstation access | Moderate | Operator access network |
| 50 | IoT | Untrusted smart devices | Highly restricted | No direct server access |
| 60 | OT-Lab | OT/ICS simulation | Explicit deny to most networks | Isolation required |
| 70 | DMZ | Public-facing workloads | Least privilege | Future use |
| 99 | Native/Untagged | Switch management only | Avoid for user workloads | Administrative only |

## Starter Outline

### 1. Segmentation Philosophy
- Default-deny posture
- Least-privilege inter-VLAN access

### 2. VLAN Definitions
- Purpose, owner, systems, address range, and gateway

### 3. Inter-VLAN Policy Matrix
- Allowed
- Denied
- Logged

### 4. Implementation Notes
- Switch trunks
- OPNsense interfaces
- DHCP scopes
- Proxmox bridge and tag strategy

### 5. Validation Plan
- Ping, traceroute, and service access tests
- OT isolation tests

## Placeholders

- Diagram placeholder: `diagrams/networking/vlan-segmentation.drawio`
- Screenshot placeholder: `screenshots/networking/opnsense-vlan-interfaces.png`
- Table placeholder: inter-VLAN rule matrix
- Configuration snippet placeholder: sanitized VLAN interface and switch trunk config

