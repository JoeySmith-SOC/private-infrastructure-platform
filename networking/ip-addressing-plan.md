# IP Addressing Plan

## Purpose

Reserve, document, and govern static addressing, DHCP scopes, gateway assignments, and naming conventions across every platform segment.

## Why This File Exists

The IP plan is a prerequisite for consistent builds, reliable monitoring, firewall policy clarity, and disaster recovery. It must be defined before nodes are installed broadly.

## Key Questions This File Must Answer

- What subnets are assigned to each VLAN or service domain?
- Which infrastructure devices require static addresses?
- What DHCP ranges are reserved for clients or lab workloads?
- What naming convention links hostnames to roles?
- How are future nodes and services added without address conflicts?

## Starter Outline

### 1. Addressing Strategy
- RFC1918 space selection
- Growth headroom
- Human-readable conventions

### 2. Subnet Allocation Table
- Gateway
- Static reservation range
- DHCP pool
- Notes

### 3. Infrastructure Static Assignments
- Firewall
- Switch
- Hypervisors
- Storage
- Monitoring
- SIEM

### 4. Naming Standards
- Hostname prefixes by role
- DNS naming expectations

### 5. Change Control
- How assignments are approved and updated

## Starter Table

| Segment | VLAN | Proposed Subnet | Gateway | Static Range | DHCP Range |
|---|---|---|---|---|---|
| Management | 10 | TBD | TBD | TBD | Minimal or none |
| Servers | 20 | TBD | TBD | TBD | Optional |
| Monitoring | 30 | TBD | TBD | TBD | Optional |
| LAN | 40 | TBD | TBD | TBD | TBD |
| IoT | 50 | TBD | TBD | TBD | TBD |
| OT-Lab | 60 | TBD | TBD | TBD | Tight scope |
| DMZ | 70 | TBD | TBD | TBD | Minimal |

## Placeholders

- Diagram placeholder: `diagrams/networking/ip-allocation-map.drawio`
- Screenshot placeholder: `screenshots/networking/dhcp-scope-summary.png`
- Table placeholder: full static assignment register
- Configuration snippet placeholder: sanitized DHCP or interface config

