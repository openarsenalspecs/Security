# GuardianNX

**GuardianNX** is a modular, AGPL-3.0+ open source home security operating system designed to eliminate vendor lock-in entirely. It combines edge AI surveillance, distributed sensor networks, encrypted communications, and autonomous response systems into a fully replaceable hardware and software ecosystem.

**Tagline:** *Always Watching, Never Intrusive.*

---

## Overview

GuardianNX is not a single product or device. It is a **distributed security framework** made of interchangeable hardware modules and open software components that work together through standardized, encrypted protocols.

It is designed to operate fully offline, partially online, or with satellite failover connectivity while maintaining full functionality at every level.

---

## Core Design Principles

- Zero vendor lock-in at every layer
- Fully modular hardware and software architecture
- Local-first processing (edge AI by default)
- End-to-end encryption for all data
- Replaceable components for every subsystem
- Open protocols only (no proprietary dependencies)
- Full system operability without cloud services

---

## Key Features

### 1. Modular Hardware System

GuardianNX is built from independent hardware modules:

- Sensor modules (motion, vibration, acoustic, UWB, mmWave)
- Vision modules (4K/IR cameras with edge AI support)
- Compute modules (Raspberry Pi, Jetson, x86, RISC-V compatible)
- Actuation modules (locks, sirens, lighting, gates)
- Communication modules (Wi-Fi, LTE/5G, satellite fallback)

Every module is replaceable and vendor-independent.

---

### 2. Edge AI Surveillance

- Local face recognition using on-device models
- Object detection using YOLO and Vision Transformer models
- Behavior anomaly detection using temporal AI models
- Audio event detection (glass break, footsteps, speech detection)
- Multi-camera fusion tracking
- No mandatory cloud processing

---

### 3. Encrypted Security Architecture

- AES-256-GCM encryption for stored data
- ChaCha20-Poly1305 for IoT communication
- Ed25519 cryptographic identity per device
- Hardware root-of-trust support (TPM/Secure Enclave)
- End-to-end encrypted event streams
- Local key management (no external dependency)

---

### 4. Intelligent Threat Response System

GuardianNX can automatically respond to detected threats:

- Lock doors and secure entry points
- Activate sirens and lighting deterrence systems
- Begin full-system camera recording
- Notify owners via encrypted alerts
- Escalate to satellite emergency communication if needed

All actions are governed by a configurable rule engine.

---

### 5. Sensor Mesh Network

- Zigbee, Thread, Matter compatibility
- UWB presence tracking for high-precision detection
- BLE mesh sensor coordination
- mmWave radar for motion detection through obstacles
- Acoustic environmental monitoring

All sensors operate in a distributed mesh network.

---

### 6. Satellite Emergency Failover

- Iridium / LEO satellite communication support
- GPS-based emergency location transmission
- Encrypted SOS message delivery
- Automatic failover when internet and cellular are unavailable

---

### 7. Fully Local Operation Mode

GuardianNX functions without internet:

- Local-only sensor operation
- Offline AI inference
- Local event logging and storage
- LAN-based access and control

---

### 8. Open Protocol Communication Layer

- MQTT event bus (primary system backbone)
- NATS / ZeroMQ for high-speed event streaming
- WireGuard-secured communication tunnels
- Matter / Thread interoperability support
- Custom GuardianNX Device Identity Protocol (GDIP)

---

### 9. Data Ownership & Portability

- All data stored in open formats (JSON, MP4, SQLite, Parquet)
- Full export capability without GuardianNX software
- No proprietary encryption tying data to vendor systems
- Self-hosted or local-only storage supported

---

### 10. AI-Powered Automation Engine

- Event-condition-action rule system
- AI-assisted automation rule suggestions
- Behavioral learning for occupancy patterns
- Multi-sensor correlation engine to reduce false alarms
- Fully local rule execution engine

---

### 11. Cross-Platform Interface System

- Web dashboard (React-based)
- Mobile application (Flutter-based)
- CLI control interface
- Local API access (REST/WebSocket)
- Real-time encrypted video streaming

---

### 12. Observability & Logging

- Real-time system monitoring
- Time-series sensor analytics (TimescaleDB)
- Event tracing and debugging tools
- Local audit logs for all system actions

---

## System Architecture

GuardianNX is composed of layered systems:

- Hardware Module Layer (sensors, cameras, actuators)
- Communication Layer (mesh + encrypted transport)
- Core Guardian Kernel (event processing engine)
- AI Processing Layer (vision, audio, anomaly detection)
- Application Layer (UI, APIs, automation rules)

All layers are independently replaceable.

---

## Specification Branding License (SBL)

### Standard
- Fully AGPL-3.0+ compliant system
- Copyleft enforced for network deployments
- Required attribution:
  - Roxanne Ardary
  - https://www.roxanneardary.com/

### Optional

- **Specification Branding License (SBL)**
  - Attribution-free commercial deployment
  - Pricing based on scale, usage, and deployment scope
  - [https://roxanneardary.com/guardiannx/](https://roxanneardary.com/guardiannx/)

---

## License & Notice Requirements

GuardianNX is released under the **GNU Affero General Public License v3.0 or later (AGPL-3.0+)**.   
By contributing to this project, you agree that your contributions will also be released under this license.

Please note the following:

- All contributions must comply with the **AGPL-3.0+** terms.  
- Under **Section 7** of the license, all redistributions, forks, and derivative works must preserve attribution to:  
  **Roxanne Ardary** and **[roxanneardary.com](https://www.roxanneardary.com/)**.  
- GuardianNX specificiations are free to use with attribution. A Specification Branding License can be negotiated upon request.
- The project's **notice.md** file tracks attribution requirements and contributor acknowledgments.   
  Any update that adds new contributors or modifies attribution should also update `notice.md`.  
- When submitting a pull request, ensure that any new files maintain the attribution headers where applicable.  
- Network-deployed versions of this software must also remain fully AGPL-3.0+ compliant, including exposure of source code modifications when applicable under the license.  

For full legal details, please refer to the AGPL-3.0+ license and the project's `notice.md` file.

---

## Project Philosophy

GuardianNX exists to ensure that home security systems remain:

- User-owned
- Fully transparent
- Technically independent
- Resistant to corporate control
- Long-term survivable without vendor dependency

---

## Summary

GuardianNX is a fully modular, encrypted, AI-powered home security operating system built to eliminate vendor lock-in entirely through open standards, replaceable hardware modules, and decentralized system design.
