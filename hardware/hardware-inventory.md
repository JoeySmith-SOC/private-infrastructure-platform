# Hardware Inventory

## Purpose

Maintain the canonical hardware inventory for the platform, including asset identity, role, purchase status, warranty, firmware, rack location, and operational notes.

## Why This File Exists

Rebuildability and lifecycle management depend on knowing exactly what hardware exists, where it lives, and what assumptions the rest of the platform makes about it.

## Key Questions This File Must Answer

- What hardware is in the platform today?
- What is purchased, installed, pending, spare, or retired?
- Where is each device located physically?
- What firmware, serial, warranty, and replacement details matter?
- Which purchases are prerequisites for later phases?

## Starter Outline

### 1. Inventory Rules
- Asset naming convention
- Status values
- Procurement update process

### 2. Core Platform Inventory
- Rack hardware
- Network hardware
- Compute nodes
- Storage hardware
- Power hardware

### 3. Procurement Tracker
- Needed
- Ordered
- Received
- Installed

### 4. Firmware and Warranty Tracking
- Version baseline
- Update cadence
- Renewal or replacement notes

## Starter Inventory Table

| Asset ID | Device | Role | Status | Rack/Location | Notes |
|---|---|---|---|---|---|
| PIP-RACK-01 | 15U Rack A | Core rack | Planned | Site TBD | Final placement pending |
| PIP-RACK-02 | 15U Rack B | Expansion rack | Planned | Site TBD | Final placement pending |
| PIP-UPS-01 | UPS | Protected power | Planned | Rack A | Size for current and near-term load |
| PIP-SW-01 | 24-port managed switch | Core switching | Planned | Rack A | Must support 802.1Q VLANs |
| PIP-FW-01 | Lenovo M720q | OPNsense firewall | Planned | Rack A | Requires Intel I350-T4 |
| PIP-NIC-01 | Intel I350-T4 | Multi-port firewall NIC | Planned | PIP-FW-01 | Confirm fit and airflow |
| PIP-PVE-01 | Lenovo Tiny node 1 | Proxmox node | Planned | Rack A/B | Exact model TBD |
| PIP-PVE-02 | Lenovo Tiny node 2 | Proxmox node | Planned | Rack A/B | Exact model TBD |
| PIP-PVE-03 | Lenovo Tiny node 3 | Proxmox node | Planned | Rack A/B | Exact model TBD |
| PIP-NAS-01 | Custom TrueNAS server | Shared storage | Planned | Rack B | Drive layout TBD |

## Placeholders

- Diagram placeholder: `diagrams/architecture/asset-map.drawio`
- Screenshot placeholder: `screenshots/architecture/hardware-inventory-dashboard.png`
- Table placeholder: serials, warranty expiry, firmware matrix
- Configuration snippet placeholder: firmware and BIOS baseline settings

