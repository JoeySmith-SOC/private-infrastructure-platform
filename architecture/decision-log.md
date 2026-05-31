# Architecture Decision Log

## Purpose

Track major architecture decisions, their rationale, tradeoffs, and status so the platform can evolve without losing design context.

## Why This File Exists

Platform projects accumulate irreversible decisions quickly. A visible decision log prevents "why did we do this?" from turning into guesswork later.

## Key Questions This File Must Answer

- Which decisions are already locked in?
- Which decisions are still open and blocking downstream work?
- What alternatives were considered?
- What tradeoffs were accepted?
- When should a decision be revisited?

## Starter Outline

### 1. Decision Logging Rules
- What qualifies as an ADR-worthy decision
- How decisions are numbered and updated

### 2. Current Decision Index
- Decided
- Proposed
- Open
- Rejected

### 3. Review Triggers
- Hardware availability changes
- Power or thermal limits
- New workload requirements

## Starter Decision Table

| ADR | Topic | Status | Initial Position | Revisit Trigger |
|---|---|---|---|---|
| ADR-001 | OPNsense on Lenovo M720q + I350-T4 | Decided | Cost-effective x86 firewall platform | If throughput or interface needs change |
| ADR-002 | Proxmox VE as primary hypervisor | Decided | Mature clustering and lab flexibility | If feature or licensing requirements shift |
| ADR-003 | TrueNAS SCALE for storage | Decided | ZFS-backed storage platform | If storage protocol or app needs change |
| ADR-004 | ZFS redundancy model | Open | Mirror vs RAIDZ1 vs RAIDZ2 | Final disk count and rebuild tolerance |
| ADR-005 | Kubernetes distribution | Open | k3s, kubeadm, RKE2, or Talos | Before Phase 4 |
| ADR-006 | OT/ICS simulation stack | Open | OpenPLC, ScadaBR, or alternative | Before Phase 5 |
| ADR-007 | GPU vendor and model | Open | NVIDIA vs AMD | Before Phase 7 |

## Placeholders

- Diagram placeholder: decision impact map
- Screenshot placeholder: ADR review board capture
- Table placeholder: decision comparison matrix
- Configuration snippet placeholder: only when a decision is finalized with sample config

