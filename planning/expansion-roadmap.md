# Expansion Roadmap

## Purpose

Describe how the platform grows from a single-rack homelab foundation into a disciplined micro-datacenter and private cloud platform across multiple phases.

## Why This File Exists

Expansion creates risk when dependencies, costs, and readiness gates are unclear. This document turns the master plan into a roadmap that shows sequencing, decision points, and what each phase must prove before the next one begins.

## Key Questions This File Must Answer

- What is the order of platform expansion and why?
- What dependencies block each phase?
- What counts as "done" before the next phase starts?
- Which future capabilities require earlier design decisions now?
- Where should cost, power, cooling, and operational complexity be reevaluated?

## Starter Outline

### 1. Roadmap Summary
- Short narrative of the platform journey from foundation to advanced workloads.

### 2. Phase Breakdown
- Phase 1: rack foundation, UPS, switch, OPNsense, first Proxmox node
- Phase 2: three-node cluster, Grafana, Wazuh, VLAN segmentation
- Phase 3: TrueNAS, backups, DR
- Phase 4: Kubernetes and automation
- Phase 5: OT/ICS security lab
- Phase 6: Mac mini integration
- Phase 7: AI and Unreal infrastructure

### 3. Readiness Gates
- Technical prerequisites
- Documentation prerequisites
- Security prerequisites
- Budget and hardware prerequisites

### 4. Cross-Phase Dependencies
- Network design
- IP/VLAN plan
- Power and cooling
- Storage and backup sizing

### 5. Review Triggers
- When to recheck rack capacity
- When to recheck UPS runtime
- When to recheck switching and storage limits

## Roadmap Snapshot

| Phase | Status | Core Deliverables | Exit Criteria |
|---|---|---|---|
| 1 | Planned | Rack, power, switch, firewall, first node | Hardware stable and documented |
| 2 | Planned | Cluster, monitoring, SIEM, VLANs | Core platform segmented and observable |
| 3 | Planned | Storage, backup, DR | Restore tests pass |
| 4 | Planned | Kubernetes, automation | Repeatable service deployment |
| 5 | Planned | OT/ICS lab | OT segment isolated and monitored |
| 6 | Planned | Mac mini layer | Additional service class integrated |
| 7 | Planned | GPU server | AI and Unreal workloads validated |

## Placeholders

- Diagram placeholder: `diagrams/architecture/phase-roadmap.drawio`
- Screenshot placeholder: `screenshots/architecture/roadmap-kanban-export.png`
- Table placeholder: phase cost and power forecast
- Configuration snippet placeholder: not expected

