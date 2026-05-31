# Network Design

## Purpose

Document the network topology, routing model, switching strategy, and segmentation design that connect the platform safely and predictably.

## Why This File Exists

The network is the foundation for every service in the platform. This file explains how traffic moves, where trust boundaries exist, and how later workloads can be added without redesigning the core.

## Known Baseline

- OPNsense firewall on Lenovo M720q
- Intel I350-T4 multi-port NIC
- 24-port managed switch
- VLAN-based segmentation
- Management, server, monitoring, user, IoT, OT, and DMZ growth path

## Key Questions This File Must Answer

- What is the physical and logical network topology?
- Which interfaces, uplinks, trunks, and access ports exist?
- How is routing handled between VLANs and to the WAN?
- What assumptions govern switch design, spanning tree, and redundancy?
- How will future workloads be integrated without weakening segmentation?

## Starter Outline

### 1. Topology Summary
- WAN edge
- Firewall
- Core switch
- Hypervisors and storage

### 2. Layer 2 Design
- VLAN trunks
- Access ports
- Native VLAN policy
- Switch management

### 3. Layer 3 Design
- OPNsense as inter-VLAN router
- DHCP and DNS responsibilities
- Default routes and north-south traffic

### 4. Service Placement
- Management interfaces
- Monitoring systems
- Infrastructure nodes
- Future DMZ and OT services

### 5. Failure Domains
- Single points of failure
- Planned mitigations

## Placeholders

- Diagram placeholder: `diagrams/networking/logical-topology.drawio`
- Diagram placeholder: `diagrams/networking/physical-topology.drawio`
- Screenshot placeholder: `screenshots/networking/switch-port-map.png`
- Table placeholder: switch port assignments
- Configuration snippet placeholder: sanitized switch trunk and access configuration

