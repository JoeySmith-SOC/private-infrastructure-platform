# OPNsense Setup

## Purpose

Document the build, configuration, hardening, and validation of the OPNsense firewall that anchors routing and security policy for the platform.

## Why This File Exists

The firewall is a foundational dependency for network segmentation, internet access, remote access, and logging. Rebuilding the environment requires a precise record of how the firewall was assembled and configured.

## Known Baseline

- Hardware: Lenovo M720q
- NIC: Intel I350-T4 4-port adapter
- Role: WAN edge, inter-VLAN routing, DHCP, DNS, VPN, policy enforcement

## Key Questions This File Must Answer

- How is the firewall hardware assembled and installed?
- How are WAN, LAN, management, and VLAN interfaces assigned?
- What baseline services must be enabled or disabled?
- What firewall rules and NAT assumptions exist?
- How is the configuration backed up and restored safely?

## Starter Outline

### 1. Hardware and BIOS Preparation
- M720q prep
- NIC install
- BIOS settings

### 2. OPNsense Installation
- Install media
- Disk layout
- Initial console setup

### 3. Interface Design
- WAN
- LAN
- Management
- VLAN subinterfaces

### 4. Baseline Services
- DNS resolver
- NTP
- DHCP scopes
- VPN
- Logging

### 5. Security Hardening
- WAN admin lockout
- MFA or strong admin policy
- Backup handling

### 6. Validation
- Internet access
- Inter-VLAN policy tests
- Remote access tests

## Placeholders

- Diagram placeholder: `diagrams/networking/opnsense-interface-map.drawio`
- Screenshot placeholder: `screenshots/firewall/opnsense-dashboard.png`
- Table placeholder: interface assignment matrix
- Configuration snippet placeholder: sanitized XML export and rule examples from `configs/firewall/opnsense/`

