# Configs

## Purpose

Store sanitized configuration exports, reference snippets, and baseline templates that support rebuilds without exposing sensitive material.

## Folder Structure

| Path | Purpose |
|---|---|
| `configs/firewall/opnsense/` | Sanitized firewall exports and rule references |
| `configs/networking/switch/` | Switch baselines and VLAN templates |
| `configs/proxmox/` | Node and cluster config references |
| `configs/storage/truenas/` | Storage service and dataset references |
| `configs/monitoring/prometheus/` | Scrape configs and alert rules |
| `configs/monitoring/grafana/` | Dashboard provisioning and datasource templates |
| `configs/security/wazuh/` | Agent and manager reference configs |
| `configs/kubernetes/` | Future manifests and cluster baselines |
| `configs/automation/` | Future Ansible, Terraform, and supporting templates |

## Rules

- Never commit live secrets, private keys, tokens, or unredacted configuration backups.
- Prefer annotated examples that explain intent over raw dumps.
- Keep filenames stable so documentation links do not drift.

