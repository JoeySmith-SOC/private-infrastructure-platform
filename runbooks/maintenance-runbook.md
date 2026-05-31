# Maintenance Runbook

## Purpose

Provide the standard operating procedure for routine maintenance, patching, upgrades, health checks, and post-change validation across the platform.

## Why This File Exists

Routine work causes avoidable outages when sequence, scope, rollback criteria, and validation are vague. This runbook standardizes normal operations.

## Key Questions This File Must Answer

- How are maintenance windows planned, communicated, and recorded?
- What checks happen before, during, and after changes?
- What patching order should be followed across firewall, hypervisors, storage, and services?
- What is the rollback trigger for a maintenance change?
- Where are outcomes, failures, and lessons logged?

## Starter Outline

### 1. Maintenance Policy
- Window frequency
- Change categories
- Approval or self-review requirements

### 2. Pre-Change Checklist
- Backups current
- Monitoring healthy
- Console access ready
- Rollback understood

### 3. Standard Maintenance Sequences
- Firewall maintenance
- Proxmox node maintenance
- TrueNAS maintenance
- Monitoring and SIEM maintenance

### 4. Post-Change Validation
- Connectivity
- Storage
- Cluster health
- Alert review

### 5. Logging and Follow-Up
- Maintenance log entry
- Documentation updates
- Lessons learned

## Placeholders

- Diagram placeholder: maintenance workflow
- Screenshot placeholder: post-maintenance health dashboard
- Table placeholder: patch cadence by platform component
- Configuration snippet placeholder: maintenance checklist template

