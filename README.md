# Private Infrastructure Platform

Private Infrastructure Platform is a long-term homelab-to-micro-datacenter build that combines infrastructure engineering, cybersecurity, OT/ICS simulation, observability, private cloud design, and future AI/GPU workloads in a single documented environment.

This repository is designed to serve three roles at the same time:

1. A build guide for standing the environment up from bare metal.
2. A runbook set for operating, maintaining, and recovering the platform.
3. A portfolio artifact that explains design decisions, tradeoffs, and outcomes clearly enough for employers, collaborators, and clients.

## Why This Project Exists

- Build a private infrastructure platform that can evolve in controlled phases instead of as disconnected lab experiments.
- Create a realistic environment for learning infrastructure, networking, IAM, virtualization, storage, monitoring, and OT/ICS security.
- Produce professional documentation that makes the system reproducible, supportable, and presentation-ready.
- Establish a foundation for future business demonstrations, client conversations, and technical case studies.

## Current Scope

- Two 15U racks
- UPS and PDU-backed power layer
- OPNsense firewall on Lenovo M720q with Intel I350-T4 NIC
- 24-port managed switch with VLAN segmentation
- Lenovo Tiny Proxmox cluster nodes
- TrueNAS storage server
- Grafana and Prometheus monitoring
- Wazuh SIEM
- Future Kubernetes, Mac mini, OT/ICS, and AI/Unreal expansion layers

## Repository Authority

- The authoritative planning source is [PROJECT_MASTER_PLAN.md](PROJECT_MASTER_PLAN.md).
- This `README.md` is the public-facing landing page and navigation guide.
- The top-level domain folders contain the operational and rebuild documentation.
- The `planning/` folder holds strategic, roadmap, and portfolio-oriented planning artifacts.

## Documentation Map

| Area | Primary Document |
|---|---|
| Vision and strategy | [planning/project-vision.md](planning/project-vision.md) |
| Architecture | [architecture/architecture-overview.md](architecture/architecture-overview.md) |
| Rack design | [architecture/rack-layout.md](architecture/rack-layout.md) |
| Hardware baseline | [hardware/hardware-inventory.md](hardware/hardware-inventory.md) |
| Network and VLANs | [networking/network-design.md](networking/network-design.md) |
| Firewall | [firewall/opnsense-setup.md](firewall/opnsense-setup.md) |
| Virtualization | [proxmox/proxmox-setup.md](proxmox/proxmox-setup.md) |
| Storage | [storage/truenas-setup.md](storage/truenas-setup.md) |
| Monitoring | [monitoring/monitoring-setup.md](monitoring/monitoring-setup.md) |
| Security and SIEM | [security/security-model.md](security/security-model.md) |
| Runbooks | [runbooks/maintenance-runbook.md](runbooks/maintenance-runbook.md) |
| Disaster recovery | [runbooks/disaster-recovery-runbook.md](runbooks/disaster-recovery-runbook.md) |
| Future roadmap | [planning/expansion-roadmap.md](planning/expansion-roadmap.md) |
| Portfolio summaries | [planning/portfolio-blog-ready-summaries.md](planning/portfolio-blog-ready-summaries.md) |

## Platform Principles

- Document before expanding.
- Segment by default, not by exception.
- Prefer repeatable builds over one-off fixes.
- Treat observability and recovery as first-class features.
- Keep public documentation sanitized, professional, and evidence-backed.

## Canonical Repository Structure

```text
private-infrastructure-platform/
|-- README.md
|-- PROJECT_MASTER_PLAN.md
|-- planning/
|-- architecture/
|-- hardware/
|-- networking/
|-- firewall/
|-- proxmox/
|-- storage/
|-- monitoring/
|-- security/
|-- kubernetes/
|-- ot-lab/
|-- runbooks/
|-- diagrams/
|-- screenshots/
|-- lessons-learned/
|-- configs/
|-- assets/
`-- logs/
```

## Build Phases

| Phase | Focus | Key Outcome |
|---|---|---|
| 1 | Rack, UPS, switch, firewall, first node | Physical and network foundation |
| 2 | Proxmox cluster, Grafana, Wazuh, VLANs | Core private cloud baseline |
| 3 | TrueNAS, backup, disaster recovery | Durable storage and recoverability |
| 4 | Kubernetes and automation | Container platform maturity |
| 5 | OT/ICS security lab | Segmented simulation environment |
| 6 | Mac mini integration | Additional platform services |
| 7 | AI and Unreal workloads | GPU-backed expansion layer |

## What This Repository Must Eventually Let You Do

- Rebuild the environment from scratch using only the repository and approved secrets.
- Understand why each architectural choice was made.
- Operate the environment safely during normal changes.
- Recover from hardware, network, storage, or service failure.
- Extend the platform without losing security boundaries or documentation quality.

## Evidence Placeholders

- Diagram placeholder: `diagrams/architecture/platform-overview.drawio`
- Diagram placeholder: `diagrams/networking/logical-topology.drawio`
- Diagram placeholder: `diagrams/rack/rack-elevation-rack-a.drawio`
- Screenshot placeholder: `screenshots/architecture/overall-platform-state.png`
- Table placeholder: hardware inventory, IP plan, VLAN matrix, backup matrix
- Config snippet placeholder: sanitized OPNsense interface assignments, Proxmox bridge config, Prometheus scrape config

## Next Documentation Priorities

1. Convert planned architecture into finalized diagrams as hardware lands.
2. Record actual serials, firmware, addresses, and rack positions in the inventory docs.
3. Capture sanitized configuration exports in `configs/`.
4. Log every maintenance window, DR test, and lesson learned as the platform matures.

