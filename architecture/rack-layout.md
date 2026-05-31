# Rack Layout

## Purpose

Document the physical placement of equipment across both 15U racks so power, cooling, cable routing, serviceability, and expansion all remain intentional.

## Why This File Exists

Physical layout decisions affect uptime, thermals, maintenance effort, and future growth. This file is the canonical reference for rack elevation, device placement, cable routing, and reserved capacity.

## Key Questions This File Must Answer

- Which devices live in each rack and at which rack units?
- How are power, networking, airflow, and cable management handled?
- What space is reserved for future Mac mini and GPU infrastructure?
- Which devices are easiest to service and why are they placed there?
- How will the rack be rebuilt if everything must be reinstalled?

## Starter Outline

### 1. Rack Strategy
- Rack A purpose
- Rack B purpose
- Separation of core services and expansion gear

### 2. Elevation Plans
- Front view
- Rear view
- RU assignments

### 3. Power Placement
- UPS position
- PDU position
- Critical versus non-critical loads

### 4. Cable Management
- Patch panel and switch adjacency
- Velcro and horizontal routing
- Fiber or copper assumptions

### 5. Expansion Reservations
- Space for TrueNAS growth
- Space for Mac minis
- Space for GPU server

## Starter Table

| Rack | RU | Device | Role | Power Source | Notes |
|---|---|---|---|---|---|
| A | TBD | UPS | Protected power | Wall + battery | Install low for stability |
| A | TBD | Managed switch | Core switching | UPS/PDU | Keep near patch management |
| A | TBD | Lenovo M720q | OPNsense firewall | UPS/PDU | Prefer easy front access |
| A/B | TBD | Lenovo Tiny nodes | Proxmox cluster | UPS/PDU | Keep clustered for cable simplicity |
| B | TBD | TrueNAS server | Shared storage | UPS/PDU | Consider airflow and drive access |

## Placeholders

- Diagram placeholder: `diagrams/rack/rack-elevation-rack-a.drawio`
- Diagram placeholder: `diagrams/rack/rack-elevation-rack-b.drawio`
- Screenshot placeholder: `screenshots/architecture/rack-front-photo-labeled.png`
- Table placeholder: full RU occupancy table
- Configuration snippet placeholder: cable label convention

