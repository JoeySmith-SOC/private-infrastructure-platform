# Architecture Overview

## Purpose

Describe the end-to-end platform architecture, including physical, logical, and operational layers, so the environment can be understood and rebuilt without relying on tribal knowledge.

## Why This File Exists

The platform spans racks, power, networking, virtualization, storage, monitoring, security, and future workload domains. This file ties those parts together and explains why the architecture is shaped this way.

## Known Baseline

| Layer | Planned Technology |
|---|---|
| Firewall and routing | OPNsense on Lenovo M720q with Intel I350-T4 |
| Switching | 24-port managed switch |
| Virtualization | Proxmox VE cluster on Lenovo Tiny nodes |
| Storage | TrueNAS custom server |
| Monitoring | Grafana and Prometheus |
| SIEM | Wazuh |
| Orchestration | Kubernetes later |
| Specialized workloads | OT/ICS lab, Mac minis, AI/GPU, Unreal later |

## Key Questions This File Must Answer

- What are the major architectural layers and trust boundaries?
- Why were these technologies selected over alternatives?
- How do physical, network, compute, storage, and security layers interact?
- Which components are foundational and which are expansion layers?
- What assumptions would force an architecture revision?

## Starter Outline

### 1. Executive Architecture Summary
- Short overview of the platform as a private infrastructure stack.

### 2. Physical Architecture
- Racks
- Power
- Cabling
- Core hardware placement

### 3. Logical Architecture
- VLANs
- Routing boundaries
- Hypervisor cluster
- Shared services

### 4. Service Architecture
- Monitoring
- SIEM
- Backup
- Remote access

### 5. Expansion Layers
- Kubernetes
- OT/ICS lab
- Mac minis
- AI/GPU server

### 6. Architectural Risks and Constraints
- Power, cooling, noise, rack space, network uplinks, storage growth

## Placeholders

- Diagram placeholder: `diagrams/architecture/platform-overview.drawio`
- Diagram placeholder: `diagrams/architecture/service-dependency-map.drawio`
- Screenshot placeholder: `screenshots/architecture/platform-state-dashboard.png`
- Table placeholder: service dependency matrix
- Configuration snippet placeholder: top-level logical topology pseudoconfig

