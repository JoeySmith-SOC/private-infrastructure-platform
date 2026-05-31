# Security Model

## Purpose

Describe the platform's security architecture, trust boundaries, identity approach, hardening posture, and monitoring controls.

## Why This File Exists

This project is partly a security learning environment, but it still needs a deliberate control model. The security model explains how the environment stays segmented, observable, and recoverable while remaining usable.

## Key Questions This File Must Answer

- What are the trust zones and threat assumptions?
- How are admin access, service access, and inter-zone communication controlled?
- What baseline hardening applies to firewall, hypervisors, storage, and services?
- How are secrets, configs, logs, and backups protected?
- How is security reviewed as new phases are added?

## Starter Outline

### 1. Threat Model Summary
- External threats
- Internal mistakes
- Lab containment risks

### 2. Trust Zones
- Management
- Servers
- Monitoring
- LAN
- IoT
- OT/ICS
- DMZ

### 3. Identity and Access
- Admin accounts
- SSH keys
- MFA
- Role separation

### 4. Control Layers
- Firewall rules
- Hardening baselines
- SIEM
- Patch management
- Backup protections

### 5. Security Review Process
- New-service intake
- Periodic policy review
- Incident lessons learned

## Placeholders

- Diagram placeholder: `diagrams/networking/security-zones.drawio`
- Screenshot placeholder: `screenshots/security/security-dashboard-overview.png`
- Table placeholder: security control matrix by layer
- Configuration snippet placeholder: sanitized hardening standards and rule examples

