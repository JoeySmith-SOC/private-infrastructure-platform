# Physical Security & Building Infrastructure

## Mission

Design, deploy, and operate a self-hosted, privacy-first physical security platform with no mandatory cloud dependency. All surveillance, recording, authentication, and management are performed locally. Internet access is disabled by default and enabled only when explicitly required for maintenance or updates. Remote access is provided only through the private infrastructure platform's controlled remote-access path.

## Design Principles

- Local-first operation
- No required cloud accounts or subscriptions
- No direct internet access for cameras or doorbell devices
- Network segmentation by default
- PoE-first camera deployment where practical
- Open protocols preferred: ONVIF and RTSP
- Dedicated security workloads and storage
- UPS-backed operation for recorder, switch, and critical network components
- Centralized logging, health monitoring, and auditability
- Configuration and recovery procedures documented before expansion

## Core Components

### Dedicated Security Server / NVR

The physical security domain should use a dedicated security server or dedicated NVR host rather than placing camera recording on a general-purpose workstation.

Target capabilities:

- Local NVR software
- Continuous and event-based recording
- Local camera management
- Hardware-accelerated video decode/encode where useful
- Local motion and object analytics
- Redundant or resilient surveillance storage
- Dual NIC or segmented network access where appropriate
- UPS protection
- Monitoring integration

The final platform may use bare-metal NVR software or a dedicated VM on suitably provisioned infrastructure. The decision must be based on storage I/O, GPU/accelerator needs, failure-domain isolation, and recovery requirements.

### Cameras

Preferred requirements:

- Wired PoE
- ONVIF support
- RTSP support
- Local web or standards-based management
- No mandatory cloud account
- No required internet connection for normal operation
- Configurable local credentials
- Ability to block outbound internet access without breaking core camera functions

### Doorbell Camera

Preferred requirements:

- Local video stream
- Local recording to the NVR
- Local event handling and notifications
- Two-way audio where practical
- ONVIF and/or RTSP when available
- No mandatory vendor cloud dependency
- Operates normally with outbound internet blocked

## Network Architecture

Create a dedicated physical-security network domain with explicit firewall policy.

Recommended logical segmentation:

- Security-Cameras VLAN: cameras and doorbell devices only
- Security-Services VLAN: NVR, analytics, and security-management services
- Management VLAN: administrative access only

Default policy:

- Cameras may communicate only with required local security services, DNS/NTP if locally provided, and explicitly approved management systems.
- Cameras and doorbell devices receive no direct internet access by default.
- Security services do not expose management interfaces to untrusted client or guest networks.
- Remote viewing must traverse the platform's approved private remote-access path rather than vendor cloud relay services.

## Storage and Retention

The physical-security platform requires a dedicated retention design.

Requirements to define before deployment:

- Camera count
- Resolution and frame rate
- Codec and bitrate targets
- Continuous versus motion/event recording
- Retention target in days
- Redundancy level
- Surveillance-grade HDD or enterprise storage selection
- Backup/export policy for critical incidents

Recorded surveillance data should not rely on a single consumer SSD or a single unprotected disk.

## Power and Availability

Critical components should be UPS-backed:

- Security server / NVR
- PoE switch powering cameras
- Firewall/router required for local routing
- Core managed switch
- Storage system if recordings depend on shared storage

Document expected runtime and graceful shutdown behavior.

## Monitoring and Security Operations

Integrate the security platform with the broader observability stack where practical:

- Device uptime and reachability
- Storage health and capacity
- Camera stream failures
- Recording failures
- NVR service health
- UPS state
- Authentication and administrative events
- Relevant alerts in Grafana, Prometheus, Wazuh, or successor tooling

## Local Analytics

Future local-only analytics may include:

- Motion detection
- Person detection
- Vehicle detection
- Package detection
- License plate recognition
- Local facial recognition only if intentionally approved and legally appropriate
- AI-assisted event summarization

Analytics should run locally where feasible and must not require camera video to be uploaded to third-party cloud services.

## Building Infrastructure Expansion

Future integrations may include:

- Access control
- Smart locks
- Garage-door state monitoring
- Environmental sensors
- Water leak detection
- Smoke/CO integration
- Intercom systems
- Energy monitoring
- Home Assistant or another locally managed automation layer

These systems should follow the same segmentation and local-first design principles.

## Recovery Requirements

The platform must document:

- NVR rebuild procedure
- Camera replacement procedure
- Camera configuration backup/export process
- Recorder configuration backup
- Storage replacement and restore process
- UPS/power-loss recovery behavior
- Network/firewall rule restoration
- Credential recovery and break-glass access

## Procurement Standard

Do not purchase physical-security hardware solely on camera resolution or price. Evaluate:

- Cloud dependency
- ONVIF/RTSP support
- PoE capability
- Local authentication
- Firmware availability
- Ability to operate with outbound internet blocked
- Compatibility with the selected NVR
- Storage and bitrate implications
- Vendor lifecycle and replacement-part availability

## Architecture Principle

Every physical-security component must justify its existence and must continue to provide its core security function without dependence on a vendor-operated internet service.
