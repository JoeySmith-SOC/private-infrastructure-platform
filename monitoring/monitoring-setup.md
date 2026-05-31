# Monitoring Setup

## Purpose

Document how observability is implemented across infrastructure, including Prometheus, Grafana, exporters, dashboards, alerting, and service health expectations.

## Why This File Exists

Monitoring turns the platform from a collection of devices into an operable environment. This file explains what is measured, how it is visualized, and how alerts drive action.

## Key Questions This File Must Answer

- What systems collect metrics and where do they run?
- Which infrastructure components expose telemetry?
- Which dashboards and alerts are required before a service is considered supported?
- How are UPS, storage, network, and cluster health observed?
- How will observability expand when Kubernetes and GPU workloads arrive?

## Starter Outline

### 1. Monitoring Goals
- Availability
- Capacity
- Performance
- Operational awareness

### 2. Core Components
- Prometheus
- Grafana
- Node exporters
- Optional UPS or storage exporters

### 3. Metric Coverage
- Firewall
- Switch
- Proxmox nodes
- TrueNAS
- Backup systems

### 4. Dashboards and Alerts
- Operator overview dashboard
- Critical threshold alerts
- Notification routing

### 5. Validation
- Test alerts
- Missing target detection
- Dashboard review process

## Placeholders

- Diagram placeholder: `diagrams/architecture/monitoring-stack.drawio`
- Screenshot placeholder: `screenshots/monitoring/grafana-overview-dashboard.png`
- Table placeholder: metrics and alert coverage matrix
- Configuration snippet placeholder: sanitized Prometheus scrape configs and Grafana provisioning files

