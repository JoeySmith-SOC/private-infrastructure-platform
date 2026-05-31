# Private Infrastructure Platform — Project Master Plan

**Repository:** `private-infrastructure-platform`
**GitHub:** https://github.com/JoeySmith-SOC/private-infrastructure-platform
**Role:** Infrastructure Project Manager / Technical Program Manager
**Last Updated:** 2026-05-31
**Status:** Phase 1 — Active Planning

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Board Columns](#board-columns)
3. [Labels and Tags](#labels-and-tags)
4. [Milestones](#milestones)
5. [Epics and Tasks](#epics-and-tasks)
   - [Phase 1 — Physical Foundation](#phase-1--physical-foundation)
   - [Phase 2 — Core Network and Firewall](#phase-2--core-network-and-firewall)
   - [Phase 3 — First Proxmox Node](#phase-3--first-proxmox-node)
   - [Phase 4 — Proxmox Cluster](#phase-4--proxmox-cluster)
   - [Phase 5 — Baseline Monitoring](#phase-5--baseline-monitoring)
   - [Phase 6 — Security Monitoring (Wazuh)](#phase-6--security-monitoring-wazuh)
   - [Phase 7 — TrueNAS Storage](#phase-7--truenas-storage)
   - [Phase 8 — Backup and Disaster Recovery](#phase-8--backup-and-disaster-recovery)
   - [Phase 9 — VLAN Segmentation](#phase-9--vlan-segmentation)
   - [Phase 10 — Kubernetes](#phase-10--kubernetes)
   - [Phase 11 — OT/ICS Security Lab](#phase-11--otics-security-lab)
   - [Phase 12 — Mac Mini Layer](#phase-12--mac-mini-layer)
   - [Phase 13 — AI and Unreal Engine Infrastructure](#phase-13--ai-and-unreal-engine-infrastructure)
   - [Phase 14 — Documentation and Portfolio Publishing](#phase-14--documentation-and-portfolio-publishing)
6. [Next 10 Tasks to Start](#next-10-tasks-to-start)
7. [Architecture Decisions Log](#architecture-decisions-log)
8. [Hardware Procurement Tracker](#hardware-procurement-tracker)

---

## Project Overview

The Private Infrastructure Platform is a multi-phase micro-datacenter and private cloud build designed for infrastructure engineering, cybersecurity, OT/ICS security, IAM lab work, Proxmox clustering, Kubernetes, TrueNAS storage, SIEM/monitoring, automation, AI, and Unreal Engine workloads.

**Core Stack:**

| Layer | Technology |
|---|---|
| Virtualization | Proxmox VE (3-node cluster) |
| Firewall/Router | OPNsense on Lenovo M720q + I350-T4 NIC |
| Switching | 24-port managed switch (VLAN-capable) |
| Storage | TrueNAS SCALE |
| Monitoring | Grafana + Prometheus |
| SIEM | Wazuh |
| Container Orchestration | Kubernetes (future) |
| OT Lab | OT/SCADA simulation (future) |
| AI/GPU | GPU server (future) |
| Mac Layer | Mac mini fleet (future) |

**Physical Footprint:**
- Two 15U racks
- Lenovo Tiny form factor cluster nodes (M920q / M720q)
- Dedicated TrueNAS storage node

---

## Board Columns

Use these columns in GitHub Projects, Linear, Jira, or any kanban tool:

| Column | Description |
|---|---|
| **Backlog** | Defined but not yet scheduled |
| **Blocked** | Waiting on hardware, dependencies, or decisions |
| **Ready** | Fully defined, unblocked, ready to execute |
| **In Progress** | Actively being worked |
| **In Review / Testing** | Validating, running acceptance criteria |
| **Done** | Complete and documented |

---

## Labels and Tags

### Priority Labels

| Label | Meaning |
|---|---|
| `P0-Critical` | Blocking all downstream work |
| `P1-High` | Required for milestone completion |
| `P2-Medium` | Important but not blocking |
| `P3-Low` | Nice to have, backlog candidate |

### Type Labels

| Label | Meaning |
|---|---|
| `hardware` | Physical procurement or installation |
| `networking` | Switch, firewall, VLAN, routing |
| `virtualization` | Proxmox, VMs, clustering |
| `storage` | TrueNAS, disks, datasets, shares |
| `security` | Firewall rules, Wazuh, hardening |
| `monitoring` | Grafana, Prometheus, alerting |
| `kubernetes` | K8s cluster, workloads, Helm |
| `ot-lab` | OT/ICS/SCADA simulation work |
| `documentation` | Docs, runbooks, diagrams |
| `automation` | Scripts, Ansible, CI/CD |
| `ai-gpu` | GPU server, AI workloads |
| `testing` | Validation, acceptance criteria checks |

### State Labels

| Label | Meaning |
|---|---|
| `do-not-start` | Explicit dependency gate |
| `awaiting-hardware` | Blocked on procurement |
| `awaiting-decision` | Needs an architecture choice |
| `portfolio-ready` | Candidate for public documentation |

---

## Milestones

| # | Milestone | Description | Prerequisite |
|---|---|---|---|
| M1 | **Rack Online** | Rack assembled, powered, cabled | — |
| M2 | **Network Core Live** | Switch and OPNsense firewall operational, internet routing working | M1 |
| M3 | **First Proxmox Node** | Single Proxmox node running VMs on the network | M2 |
| M4 | **Proxmox Cluster** | Three-node HA cluster operational | M3 |
| M5 | **Monitoring Online** | Grafana + Prometheus scraping all nodes | M4 |
| M6 | **Wazuh SIEM Live** | Wazuh server deployed with agents on all major nodes | M5 |
| M7 | **TrueNAS Storage** | TrueNAS online, sharing storage to cluster | M4 |
| M8 | **Backup Strategy Active** | Automated backups running for all critical VMs and data | M7 |
| M9 | **Network Segmented** | Full VLAN architecture implemented and enforced | M6 |
| M10 | **Kubernetes Cluster** | K8s cluster running, core workloads deployed | M9 |
| M11 | **OT Lab Active** | OT/ICS simulation environment running in isolated segment | M9 |
| M12 | **Mac Mini Layer** | Mac minis integrated into platform | M10 |
| M13 | **AI/GPU Infrastructure** | GPU server online, AI workloads running | M12 |
| M14 | **Portfolio Published** | Public-facing documentation and case study complete | M13 |

---

## Epics and Tasks

---

### Phase 1 — Physical Foundation

**Epic Goal:** Racks assembled, powered, and ready for hardware installation.
**Milestone:** M1
**Labels:** `hardware`, `P0-Critical`

---

#### EPIC-001: Rack Procurement and Assembly

**Acceptance Criteria:**
- Both 15U racks are assembled and stable
- Rack units are inventoried and labeled
- Rack placement is finalized and documented

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-001 | Decide on rack placement location (room, orientation, airflow) | P0 | Document in `planning/architecture/` |
| T-002 | Procure or confirm availability of both 15U racks | P0 | Log in hardware tracker |
| T-003 | Assemble racks according to manufacturer instructions | P0 | — |
| T-004 | Install rack shelves, blanking panels, and cable management rails | P1 | — |
| T-005 | Label each rack unit slot (1U through 15U) on both racks | P2 | Create rack elevation diagram |
| T-006 | Document rack layout diagram in `diagrams/` | P2 | Use draw.io, Visio, or ASCII |

---

#### EPIC-002: Power and UPS

**Acceptance Criteria:**
- UPS is installed and tested
- All critical equipment is on UPS-protected outlets
- Runtime estimate is documented
- Power draw per device is estimated and recorded

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-007 | Procure UPS unit (confirm VA rating covers full load) | P0 | Recommend 1500VA+ for Phase 1 |
| T-008 | Install UPS in rack | P0 | — |
| T-009 | Map all devices to UPS vs. non-UPS outlets | P1 | — |
| T-010 | Test UPS failover with simulated power loss | P1 | Document runtime at load |
| T-011 | Configure UPS network management (NUT or vendor agent) | P2 | Future integration with monitoring |
| T-012 | Document power draw estimates per device in `planning/hardware/` | P2 | — |

**Do Not Start:** T-008 until T-007 is complete.

---

#### EPIC-003: Cable Management and Physical Organization

**Acceptance Criteria:**
- All patch cables are labeled at both ends
- Cable runs are clean, routed, and secured
- No unlabeled cables in the rack

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-013 | Procure patch cables (Cat6 or Cat6A, appropriate lengths) | P1 | Buy multiple lengths |
| T-014 | Procure cable management panels and Velcro ties | P2 | — |
| T-015 | Label all patch cables at both ends | P1 | Use label maker or tags |
| T-016 | Route and dress all cables neatly | P1 | — |
| T-017 | Document physical cable map in `planning/networking/` | P2 | — |

---

### Phase 2 — Core Network and Firewall

**Epic Goal:** Managed switch and OPNsense firewall are operational with internet routing working.
**Milestone:** M2
**Labels:** `networking`, `P0-Critical`
**Do Not Start:** Until M1 is complete.

---

#### EPIC-004: Managed Switch Deployment

**Acceptance Criteria:**
- Switch is installed and powered
- Management interface is accessible
- All active ports are inventoried
- Uplink to ISP/modem is functional

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-018 | Procure or confirm 24-port managed switch | P0 | Must support 802.1Q VLANs |
| T-019 | Install switch in rack | P0 | — |
| T-020 | Access switch management interface and change default credentials | P0 | Document credentials in password manager |
| T-021 | Map all switch ports to devices in `planning/networking/` | P1 | — |
| T-022 | Configure uplink port to ISP modem/ONT | P0 | — |
| T-023 | Enable spanning tree (STP/RSTP) to prevent loops | P1 | — |
| T-024 | Document switch configuration baseline | P1 | Save config backup to repo |

---

#### EPIC-005: OPNsense Firewall Deployment

**Acceptance Criteria:**
- OPNsense installed on Lenovo M720q with I350-T4 NIC
- WAN and LAN interfaces configured
- Internet routing through OPNsense is functional
- Default firewall rules documented
- Admin console accessible only from management network

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-025 | Procure Lenovo M720q (if not already owned) | P0 | Log in hardware tracker |
| T-026 | Procure Intel I350-T4 NIC (4-port) | P0 | Confirm PCIe slot compatibility |
| T-027 | Install I350-T4 NIC in M720q | P0 | — |
| T-028 | Install OPNsense on M720q (USB boot → disk install) | P0 | Use current stable release |
| T-029 | Assign WAN interface (uplink from switch or modem) | P0 | — |
| T-030 | Assign LAN interface for main network | P0 | — |
| T-031 | Assign dedicated management interface (future OOB) | P1 | — |
| T-032 | Verify internet access through OPNsense | P0 | Test from client device |
| T-033 | Configure NTP on OPNsense | P1 | Time sync is critical for security logs |
| T-034 | Configure DNS resolver in OPNsense | P1 | Enable DNSSEC |
| T-035 | Disable remote admin access on WAN | P0 | Security baseline |
| T-036 | Export and commit OPNsense config backup to `planning/firewall/` | P1 | Scrub secrets before committing |
| T-037 | Document firewall architecture in `planning/firewall/` | P1 | — |

**Do Not Start:** T-028 until T-027 is complete. T-032 requires T-029 and T-030.

---

### Phase 3 — First Proxmox Node

**Epic Goal:** First Proxmox VE node is installed, joined to the network, and running VMs.
**Milestone:** M3
**Labels:** `virtualization`, `P0-Critical`
**Do Not Start:** Until M2 is complete.

---

#### EPIC-006: First Proxmox Node Setup

**Acceptance Criteria:**
- Proxmox VE installed on first Lenovo Tiny node
- Node accessible via web UI from management network
- VM creation tested with at least one test VM
- Storage pool configured
- Node hardened (SSH keys, root login restricted)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-038 | Procure first Lenovo M920q or M720q cluster node | P0 | Log in hardware tracker |
| T-039 | Install Proxmox VE on node (USB boot → disk install) | P0 | Use current stable release |
| T-040 | Set static IP for Proxmox node | P0 | Plan full IP address scheme first |
| T-041 | Access Proxmox web UI and verify node health | P0 | — |
| T-042 | Configure local storage pool (LVM or ZFS) | P1 | Prefer ZFS for data integrity |
| T-043 | Configure Proxmox network bridge for VM networking | P1 | — |
| T-044 | Harden Proxmox node (disable root SSH login, add SSH keys) | P1 | Document in `planning/proxmox/` |
| T-045 | Create and boot a test VM (e.g., Ubuntu Server) | P1 | Validate VM networking end-to-end |
| T-046 | Remove test VM after validation | P2 | Keep environment clean |
| T-047 | Document node baseline config in `planning/proxmox/` | P1 | — |

---

#### EPIC-007: IP Address Scheme and DNS Planning

**Acceptance Criteria:**
- Full IP address plan documented
- Subnet allocations defined per function
- Internal DNS plan drafted

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-048 | Define subnet allocations (management, servers, VMs, IoT, OT, etc.) | P0 | Do before deploying any node |
| T-049 | Define static IP assignments for all infrastructure nodes | P0 | — |
| T-050 | Document IP scheme in `planning/networking/ip-scheme.md` | P0 | — |
| T-051 | Plan internal DNS domain (e.g., `lab.local` or `infra.internal`) | P1 | — |
| T-052 | Document DNS plan in `planning/networking/dns.md` | P1 | — |

**Do Not Start:** T-039 until T-048 is complete.

---

### Phase 4 — Proxmox Cluster

**Epic Goal:** Three-node Proxmox HA cluster is operational with live migration working.
**Milestone:** M4
**Labels:** `virtualization`, `P1-High`
**Do Not Start:** Until M3 is complete.

---

#### EPIC-008: Proxmox Three-Node Cluster

**Acceptance Criteria:**
- All three nodes in the same Proxmox cluster
- Quorum is healthy with three votes
- Live migration tested between nodes
- HA group configured for critical VMs
- Shared storage accessible from all nodes (or replicated storage configured)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-053 | Procure nodes 2 and 3 (Lenovo M920q / M720q) | P0 | Log in hardware tracker |
| T-054 | Install Proxmox VE on nodes 2 and 3 | P0 | Use same version as node 1 |
| T-055 | Set static IPs on nodes 2 and 3 per IP scheme | P0 | — |
| T-056 | Create Proxmox cluster from node 1 | P0 | — |
| T-057 | Join nodes 2 and 3 to cluster | P0 | — |
| T-058 | Verify quorum is healthy (pvecm status) | P0 | 3 nodes = 3 votes |
| T-059 | Configure separate cluster network (if possible) | P1 | Dedicated corosync traffic |
| T-060 | Test live VM migration between nodes | P1 | Requires shared or replicated storage |
| T-061 | Configure HA groups for critical VMs | P1 | — |
| T-062 | Document cluster architecture in `planning/proxmox/cluster.md` | P1 | — |
| T-063 | Test simulated node failure and HA recovery | P2 | — |

**Do Not Start:** T-056 until T-040, T-055 are complete and IP scheme is finalized.

---

### Phase 5 — Baseline Monitoring

**Epic Goal:** Grafana and Prometheus are deployed and scraping all infrastructure nodes.
**Milestone:** M5
**Labels:** `monitoring`, `P1-High`
**Do Not Start:** Until M4 is complete.

---

#### EPIC-009: Prometheus Deployment

**Acceptance Criteria:**
- Prometheus running (VM or container on Proxmox)
- Node exporters on all Proxmox nodes
- Prometheus scraping all targets and showing data

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-064 | Create dedicated monitoring VM on Proxmox (Ubuntu Server) | P1 | 2 vCPU, 4GB RAM minimum |
| T-065 | Install Prometheus on monitoring VM | P1 | Consider Docker Compose stack |
| T-066 | Install node_exporter on all Proxmox nodes | P1 | — |
| T-067 | Configure Prometheus scrape targets for all nodes | P1 | — |
| T-068 | Verify Prometheus targets are UP | P1 | Check /targets endpoint |
| T-069 | Document Prometheus config in `planning/monitoring/` | P2 | — |

---

#### EPIC-010: Grafana Deployment

**Acceptance Criteria:**
- Grafana running and accessible
- Connected to Prometheus data source
- Node health dashboards deployed
- Alert rules defined for critical metrics (disk, memory, CPU)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-070 | Install Grafana on monitoring VM | P1 | Same VM as Prometheus or separate |
| T-071 | Connect Grafana to Prometheus data source | P1 | — |
| T-072 | Import Node Exporter Full dashboard (ID 1860) | P1 | Grafana.com dashboard library |
| T-073 | Import Proxmox dashboard | P1 | — |
| T-074 | Create custom overview dashboard (all nodes at a glance) | P2 | — |
| T-075 | Configure alerting (email or webhook) for critical thresholds | P2 | Disk >85%, memory >90%, node down |
| T-076 | Document Grafana setup and dashboards in `planning/monitoring/` | P2 | — |

---

### Phase 6 — Security Monitoring (Wazuh)

**Epic Goal:** Wazuh SIEM deployed with agents on all infrastructure nodes.
**Milestone:** M6
**Labels:** `security`, `monitoring`, `P1-High`
**Do Not Start:** Until M5 is complete.

---

#### EPIC-011: Wazuh SIEM Deployment

**Acceptance Criteria:**
- Wazuh manager deployed (VM on Proxmox)
- Wazuh agents installed on all active nodes
- Wazuh dashboard accessible
- Basic alert rules active (authentication, file integrity, CVE scanning)
- Log retention policy configured

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-077 | Create dedicated Wazuh VM on Proxmox | P1 | 4 vCPU, 8GB RAM minimum |
| T-078 | Install Wazuh manager (all-in-one or distributed) | P1 | Use official installer |
| T-079 | Access Wazuh dashboard and verify manager health | P1 | — |
| T-080 | Install Wazuh agent on all Proxmox nodes | P1 | — |
| T-081 | Install Wazuh agent on OPNsense firewall (if supported) | P2 | — |
| T-082 | Verify agents are reporting to manager | P1 | — |
| T-083 | Enable file integrity monitoring (FIM) on critical paths | P1 | /etc, /var/log |
| T-084 | Configure vulnerability detection scan | P2 | — |
| T-085 | Define log retention policy | P1 | Balance storage vs. compliance |
| T-086 | Document Wazuh deployment in `planning/security/` | P2 | — |

---

### Phase 7 — TrueNAS Storage

**Epic Goal:** TrueNAS SCALE online with storage shared to the Proxmox cluster.
**Milestone:** M7
**Labels:** `storage`, `P1-High`
**Do Not Start:** Until M4 is complete.

---

#### EPIC-012: TrueNAS SCALE Deployment

**Acceptance Criteria:**
- TrueNAS SCALE installed on dedicated storage node
- ZFS pool created and healthy
- NFS and/or SMB shares configured
- Proxmox cluster connected to TrueNAS storage
- S.M.A.R.T. monitoring enabled on all drives

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-087 | Procure TrueNAS storage node hardware (or repurpose existing) | P1 | Log in hardware tracker |
| T-088 | Procure storage drives (HDD or SSD, decide per use case) | P1 | Decide raidz1/raidz2/mirror |
| T-089 | Install TrueNAS SCALE on storage node | P1 | Use USB boot drive for OS |
| T-090 | Access TrueNAS web UI and set static IP | P1 | — |
| T-091 | Create ZFS pool with appropriate redundancy level | P0 | Document decision in ADR |
| T-092 | Create datasets for VM storage, backups, and general file storage | P1 | — |
| T-093 | Configure NFS share for Proxmox storage | P1 | Add to Proxmox as NFS storage |
| T-094 | Configure SMB share for general file access | P2 | — |
| T-095 | Enable S.M.A.R.T. monitoring and test alerts | P1 | — |
| T-096 | Add TrueNAS NFS storage to Proxmox cluster | P1 | — |
| T-097 | Test VM creation on TrueNAS-backed storage | P1 | — |
| T-098 | Document TrueNAS architecture and ZFS layout in `planning/storage/` | P1 | — |

**Do Not Start:** T-091 before ZFS redundancy decision is made and documented.

---

### Phase 8 — Backup and Disaster Recovery

**Epic Goal:** Automated backups running for all critical VMs and datasets.
**Milestone:** M8
**Labels:** `storage`, `security`, `P1-High`
**Do Not Start:** Until M7 is complete.

---

#### EPIC-013: VM Backup Strategy

**Acceptance Criteria:**
- Proxmox Backup Server (PBS) deployed
- All critical VMs included in automated backup schedule
- Backup restore tested successfully
- Retention policy documented

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-099 | Deploy Proxmox Backup Server (PBS) VM or dedicated node | P1 | Can be on TrueNAS storage |
| T-100 | Connect PBS to Proxmox cluster | P1 | — |
| T-101 | Define backup schedule for all critical VMs | P1 | Daily minimum for critical VMs |
| T-102 | Run first backup job and verify completion | P1 | — |
| T-103 | Test restore of a critical VM from backup | P0 | Restore to different node to validate |
| T-104 | Document backup schedule and retention policy in `planning/storage/backup-strategy.md` | P1 | — |

---

#### EPIC-014: TrueNAS Dataset Snapshots

**Acceptance Criteria:**
- ZFS snapshot schedules configured for all datasets
- Snapshots verifiable and restorable
- Off-site or secondary backup plan documented

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-105 | Configure ZFS snapshot schedules in TrueNAS | P1 | Daily snapshots, 30-day retention |
| T-106 | Test snapshot restore of a dataset | P1 | — |
| T-107 | Research and document off-site backup option | P2 | Backblaze B2, rsync, or secondary node |
| T-108 | Document disaster recovery procedure in `runbooks/dr-recovery.md` | P1 | Step-by-step from bare metal |

---

### Phase 9 — VLAN Segmentation

**Epic Goal:** Full VLAN architecture implemented across switch and OPNsense, with inter-VLAN firewall rules enforced.
**Milestone:** M9
**Labels:** `networking`, `security`, `P1-High`
**Do Not Start:** Until M6 and M7 are complete (stable environment before segmenting).

---

#### EPIC-015: VLAN Design and Implementation

**Acceptance Criteria:**
- VLAN IDs assigned for each network segment
- VLANs configured on managed switch
- OPNsense VLAN interfaces and firewall rules configured
- Proxmox VMs assigned to correct VLANs
- Inter-VLAN routing enforced by OPNsense rules (not default-allow)
- OT lab VLAN isolated with explicit deny rules

**Recommended VLAN Design:**

| VLAN ID | Name | Purpose |
|---|---|---|
| 10 | Management | Infrastructure management interfaces |
| 20 | Servers | Proxmox VMs, TrueNAS, PBS |
| 30 | Monitoring | Grafana, Prometheus, Wazuh |
| 40 | LAN | General workstations |
| 50 | IoT | Smart devices, isolated |
| 60 | OT-Lab | OT/ICS simulation, strictly isolated |
| 70 | DMZ | Public-facing services |
| 99 | Native/Untagged | Switch management only |

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-109 | Finalize and document VLAN design in `planning/networking/vlan-design.md` | P0 | Must be approved before any switch config |
| T-110 | Configure VLANs on managed switch | P0 | — |
| T-111 | Configure trunk ports between switch and OPNsense | P0 | — |
| T-112 | Create VLAN interfaces in OPNsense | P0 | — |
| T-113 | Assign DHCP scopes per VLAN in OPNsense | P1 | — |
| T-114 | Write inter-VLAN firewall rules (default-deny, explicit-allow) | P0 | Start restrictive |
| T-115 | Assign existing Proxmox VMs to correct VLANs | P1 | — |
| T-116 | Verify OT VLAN is fully isolated (no inter-VLAN path) | P0 | Test with traceroute/ping |
| T-117 | Test management access from VLAN 10 to all devices | P1 | — |
| T-118 | Document final VLAN and firewall rule set in `planning/firewall/` | P1 | — |

**Do Not Start:** Any switch/OPNsense VLAN config until T-109 is fully documented and reviewed.

---

### Phase 10 — Kubernetes

**Epic Goal:** Kubernetes cluster running on Proxmox with core workloads deployed.
**Milestone:** M10
**Labels:** `kubernetes`, `P2-Medium`
**Do Not Start:** Until M9 is complete (network segmentation required before K8s).

---

#### EPIC-016: Kubernetes Cluster Deployment

**Acceptance Criteria:**
- K8s cluster deployed on Proxmox VMs (3 nodes minimum)
- kubectl access working from management machine
- Core infrastructure workloads deployed (ingress controller, cert-manager)
- Persistent storage connected (TrueNAS via NFS or iSCSI)
- Cluster accessible only from management VLAN

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-119 | Decide K8s distribution (kubeadm, k3s, RKE2, Talos) | P1 | Document decision in ADR |
| T-120 | Provision K8s node VMs on Proxmox (3 nodes) | P1 | Use templates for repeatability |
| T-121 | Install and configure chosen K8s distribution | P1 | — |
| T-122 | Configure kubeconfig and verify cluster health | P1 | — |
| T-123 | Deploy ingress controller (nginx or Traefik) | P1 | — |
| T-124 | Deploy cert-manager for TLS management | P2 | — |
| T-125 | Configure persistent volume claim via TrueNAS storage class | P1 | — |
| T-126 | Deploy a test workload and verify end-to-end | P1 | — |
| T-127 | Configure Prometheus to scrape K8s cluster metrics | P2 | — |
| T-128 | Document K8s architecture in `planning/kubernetes/` | P1 | — |

---

### Phase 11 — OT/ICS Security Lab

**Epic Goal:** Isolated OT/ICS simulation environment running for security research.
**Milestone:** M11
**Labels:** `ot-lab`, `security`, `P2-Medium`
**Do Not Start:** Until M9 is complete (VLAN 60 must be fully isolated before this phase starts).

---

#### EPIC-017: OT/ICS Lab Environment

**Acceptance Criteria:**
- OT lab VLAN 60 is confirmed isolated from all other segments
- OT simulation software running (e.g., ScadaBR, OpenPLC, or Factorio-style sim)
- At least one simulated ICS protocol reachable within the VLAN (Modbus or DNP3)
- Wazuh monitoring active on OT segment
- No path from OT VLAN to internet (explicit deny verified)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-129 | Confirm VLAN 60 isolation with firewall rule audit | P0 | Block list: all inter-VLAN and WAN |
| T-130 | Deploy OT simulation VM (OpenPLC, ScadaBR, or similar) | P1 | — |
| T-131 | Configure simulated Modbus TCP or DNP3 endpoint | P1 | — |
| T-132 | Deploy attacker simulation VM in OT VLAN for testing | P2 | Kali or similar |
| T-133 | Install Wazuh agent on OT VMs | P1 | — |
| T-134 | Simulate an OT attack scenario and verify Wazuh detection | P2 | Document findings |
| T-135 | Document OT lab topology and scenarios in `planning/ot-lab/` | P1 | — |

---

### Phase 12 — Mac Mini Layer

**Epic Goal:** Mac mini fleet integrated into the platform for macOS workloads, CI, or dev infrastructure.
**Milestone:** M12
**Labels:** `hardware`, `P3-Low`
**Do Not Start:** Until M10 is complete.

---

#### EPIC-018: Mac Mini Integration

**Acceptance Criteria:**
- Mac minis physically installed in rack (shelf or mount)
- Assigned to server VLAN with static IPs
- SSH access configured
- Wazuh agent deployed on each
- Use case defined and documented

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-136 | Define use case for Mac mini layer (CI runners, macOS dev, etc.) | P1 | Document decision before procurement |
| T-137 | Procure Mac minis (define quantity and spec) | P1 | Log in hardware tracker |
| T-138 | Install in rack (shelf or dedicated mount) | P1 | — |
| T-139 | Assign static IPs and connect to server VLAN | P1 | — |
| T-140 | Configure SSH access and deploy SSH keys | P1 | — |
| T-141 | Install Wazuh agent | P2 | — |
| T-142 | Install management tooling (Ansible inventory, MDM, or manual) | P2 | — |
| T-143 | Document Mac mini integration in `planning/architecture/` | P2 | — |

---

### Phase 13 — AI and Unreal Engine Infrastructure

**Epic Goal:** GPU server online with AI workloads and Unreal Engine build infrastructure running.
**Milestone:** M13
**Labels:** `ai-gpu`, `P3-Low`
**Do Not Start:** Until M12 is complete.

---

#### EPIC-019: GPU Server Deployment

**Acceptance Criteria:**
- GPU server installed in rack
- CUDA/ROCm drivers installed and validated
- Wazuh agent deployed
- At least one AI workload running (local LLM, Stable Diffusion, or similar)
- Unreal Engine build pipeline connected (if applicable)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-144 | Define GPU server specs (NVIDIA vs AMD, VRAM requirements) | P1 | Document decision in ADR |
| T-145 | Procure GPU server | P1 | Log in hardware tracker |
| T-146 | Install in rack and connect to power and network | P1 | — |
| T-147 | Install OS (Ubuntu Server with GPU drivers) | P1 | — |
| T-148 | Validate GPU with cuda-smi or nvidia-smi | P1 | — |
| T-149 | Deploy local LLM (Ollama, llama.cpp, or similar) | P2 | — |
| T-150 | Connect to Grafana monitoring (GPU metrics via dcgm-exporter) | P2 | — |
| T-151 | Install Wazuh agent | P2 | — |
| T-152 | Document GPU server in `planning/architecture/` | P2 | — |

---

### Phase 14 — Documentation and Portfolio Publishing

**Epic Goal:** All infrastructure documentation published and portfolio-ready.
**Milestone:** M14
**Labels:** `documentation`, `portfolio-ready`, `P2-Medium`
**Do Not Start:** As a full phase, wait until M13. Documentation tasks within each phase should be done continuously.

---

#### EPIC-020: Documentation Completion and Repository Polish

**Acceptance Criteria:**
- All `planning/` directories have complete documentation
- All runbooks written for critical recovery procedures
- Architecture diagrams published
- README.md is a polished project overview
- Repository is public-ready (no secrets, no stubs)

| Task ID | Task | Priority | Notes |
|---|---|---|---|
| T-153 | Write `README.md` as professional project overview | P1 | Treat as public portfolio landing page |
| T-154 | Write runbooks for: node failure, disk failure, network outage, VM restore | P1 | In `runbooks/` |
| T-155 | Create architecture diagram (full platform view) | P1 | In `diagrams/` |
| T-156 | Create network topology diagram | P1 | In `diagrams/` |
| T-157 | Create rack elevation diagrams for both racks | P2 | In `diagrams/` |
| T-158 | Document all lessons learned per phase in `lessons-learned/` | P2 | Honest post-mortems are valuable |
| T-159 | Audit repo for any secrets, passwords, or credentials before publishing | P0 | Block publish until clean |
| T-160 | Publish repository and share as portfolio piece | P1 | — |

---

## Next 10 Tasks to Start

These are the first 10 tasks in technical order. Nothing below this list should be started until these are complete or in progress.

| # | Task ID | Task | Why Now |
|---|---|---|---|
| 1 | T-048 | Define subnet allocations and IP scheme | Foundation for every IP assignment going forward |
| 2 | T-001 | Decide rack placement (airflow, room, orientation) | Must be resolved before any hardware installs |
| 3 | T-007 | Procure and install UPS | No hardware goes in a rack without power protection |
| 4 | T-018 | Procure and install managed switch | Core network dependency for all other nodes |
| 5 | T-025 | Procure OPNsense hardware (M720q + I350-T4 NIC) | Firewall must be up before any node is internet-exposed |
| 6 | T-038 | Procure first Proxmox node (M920q or M720q) | First compute node for the cluster |
| 7 | T-109 | Design and document VLAN architecture | Must be planned before switch config, even if not implemented yet |
| 8 | T-006 | Create rack elevation diagram | Visual reference for all physical placement decisions |
| 9 | T-050 | Document IP scheme in `planning/networking/ip-scheme.md` | Written documentation before any device gets an IP |
| 10 | T-024 | Document switch configuration baseline | Capture clean state immediately after switch config |

---

## Architecture Decisions Log

Track every significant infrastructure decision here. Move detailed ADRs to `planning/architecture/`.

| ADR # | Decision | Status | Date | Notes |
|---|---|---|---|---|
| ADR-001 | OPNsense on Lenovo M720q with I350-T4 NIC | Decided | — | Cost-effective, x86, strong community |
| ADR-002 | Proxmox VE as hypervisor | Decided | — | Open source, enterprise-grade clustering |
| ADR-003 | TrueNAS SCALE for storage | Decided | — | ZFS, NFS/SMB, active development |
| ADR-004 | ZFS redundancy level for storage pool | **Open** | — | Choose between raidz1, raidz2, mirror |
| ADR-005 | Kubernetes distribution | **Open** | — | kubeadm vs k3s vs RKE2 vs Talos |
| ADR-006 | OT simulation software | **Open** | — | OpenPLC, ScadaBR, or other |
| ADR-007 | GPU vendor and model | **Open** | — | NVIDIA vs AMD based on workload needs |
| ADR-008 | Mac mini use case | **Open** | — | CI runners, dev infra, or other |

---

## Hardware Procurement Tracker

| Item | Purpose | Status | Location | Notes |
|---|---|---|---|---|
| 2x 15U Rack | Physical housing | — | — | — |
| UPS | Power protection | — | — | Determine VA rating based on load estimate |
| 24-port Managed Switch | Core switching | — | — | Must support 802.1Q VLANs |
| Lenovo M720q (Firewall) | OPNsense firewall node | — | — | — |
| Intel I350-T4 NIC | OPNsense multi-port NIC | — | — | Confirm PCIe slot available in M720q |
| Lenovo M920q/M720q (Node 1) | Proxmox node 1 | — | — | — |
| Lenovo M920q/M720q (Node 2) | Proxmox node 2 | — | — | — |
| Lenovo M920q/M720q (Node 3) | Proxmox node 3 | — | — | — |
| TrueNAS storage node | Dedicated NAS | — | — | Needs multiple drives |
| Storage drives | ZFS pool | — | — | Decide count and redundancy first |
| Mac minis | macOS layer | — | — | Quantity and spec TBD |
| GPU server | AI/Unreal workloads | — | — | Spec TBD |
| Cat6/Cat6A patch cables | Rack cabling | — | — | Multiple lengths |
| Cable management panels | Physical organization | — | — | — |

---

*This document is the authoritative planning source for the Private Infrastructure Platform. All architecture decisions, hardware purchases, and phase completions must be reflected here or in linked documents within the repository.*
