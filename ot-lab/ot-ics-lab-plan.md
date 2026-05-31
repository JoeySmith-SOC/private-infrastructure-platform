# OT/ICS Lab Plan

## Purpose

Define how the OT/ICS simulation environment will be isolated, instrumented, and used for safe security experimentation inside the broader platform.

## Why This File Exists

OT/ICS workloads introduce unique protocol, segmentation, and containment requirements. This plan ensures the lab supports learning without weakening the rest of the environment.

## Key Questions This File Must Answer

- What is the purpose of the OT/ICS lab in this platform?
- Which tools, protocols, and scenarios will be simulated?
- How is the OT segment isolated from management, server, and internet zones?
- What logging and detection coverage is required?
- What safety rules govern offensive testing inside the lab?

## Starter Outline

### 1. Lab Objectives
- Protocol familiarity
- Detection engineering
- Segmentation validation

### 2. Candidate Tooling
- OpenPLC
- ScadaBR
- Modbus TCP simulations
- Attacker simulation hosts

### 3. Network and Security Design
- VLAN 60 isolation
- Explicit deny rules
- Monitoring placement

### 4. Scenario Catalog
- Normal operations
- Misconfiguration
- Unauthorized access
- Malware or protocol abuse simulation

### 5. Evidence and Review
- Lab findings
- Detection tuning
- Lessons learned

## Placeholders

- Diagram placeholder: `diagrams/ot-lab/ot-lab-topology.drawio`
- Screenshot placeholder: `screenshots/ot-lab/ot-simulation-dashboard.png`
- Table placeholder: scenario and detection matrix
- Configuration snippet placeholder: sanitized OT VM network and service definitions

