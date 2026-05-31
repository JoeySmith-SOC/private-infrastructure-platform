# Wazuh SIEM Setup

## Purpose

Document the architecture, deployment, agent strategy, detections, and operational care for the Wazuh SIEM layer.

## Why This File Exists

Security monitoring needs to be planned like a platform service, not added as an afterthought. This file captures how Wazuh is deployed and how it supports infrastructure, OT/ICS, and future workload visibility.

## Key Questions This File Must Answer

- Where does the Wazuh manager run and how is it protected?
- Which systems require agents and what telemetry is expected from each?
- What alerting, file integrity, and vulnerability workflows are enabled?
- How are retention, storage, and tuning handled?
- How does Wazuh integrate with OT/ICS and future Kubernetes workloads?

## Starter Outline

### 1. SIEM Objectives
- Detection coverage
- Integrity monitoring
- Vulnerability visibility

### 2. Deployment Model
- Manager placement
- Agent enrollment
- Access controls

### 3. Coverage Plan
- Firewall
- Hypervisors
- Storage
- Monitoring nodes
- OT assets

### 4. Rule and Policy Baseline
- Authentication events
- File integrity
- Vulnerability scanning
- Custom lab detections

### 5. Operations
- Retention
- Tuning
- Incident escalation paths

## Placeholders

- Diagram placeholder: `diagrams/architecture/wazuh-deployment.drawio`
- Screenshot placeholder: `screenshots/security/wazuh-agent-overview.png`
- Table placeholder: Wazuh agent coverage matrix
- Configuration snippet placeholder: sanitized agent enrollment and policy examples

