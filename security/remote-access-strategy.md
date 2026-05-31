# Remote Access Strategy

## Purpose

Define how administrators securely reach the platform from inside and outside the local environment for management, emergency access, and operational support.

## Why This File Exists

Remote access is convenient, but it is also one of the highest-risk parts of an infrastructure platform. This strategy balances reachability, security, auditability, and recovery.

## Key Questions This File Must Answer

- Which remote access methods are allowed and which are prohibited?
- What role does OPNsense VPN play in administration?
- How is MFA, device trust, and credential management enforced?
- What is the break-glass path if the primary access method fails?
- How are access logs reviewed and retained?

## Starter Outline

### 1. Access Objectives
- Secure administration
- Minimal exposed surface area
- Auditability

### 2. Approved Access Paths
- Local management VLAN
- VPN
- Bastion or jump host if introduced later

### 3. Identity and Device Controls
- MFA
- SSH keys
- Password manager
- Admin workstation standards

### 4. Emergency Access
- Break-glass accounts
- Console access
- On-site recovery

### 5. Logging and Review
- Firewall logs
- VPN logs
- Authentication audit process

## Placeholders

- Diagram placeholder: remote administration flow
- Screenshot placeholder: VPN client or firewall access policy capture
- Table placeholder: access method approval matrix
- Configuration snippet placeholder: sanitized VPN and SSH policy examples

