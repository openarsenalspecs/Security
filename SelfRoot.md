# SelfRoot

SelfRoot is an open-source deterministic identity infrastructure system designed to provide passwordless authentication and identity verification through locally processed biometric presence and cryptographic proof.

**Deterministic Identity Infrastructure**

SelfRoot is designed around a modular architecture. Core security, identity, biometric, cryptographic, and verification capabilities are implemented as core modules, while integrations, additional biometric modalities, deployment targets, and specialized authentication methods can be added through optional plugin modules.

---

## Core Principles

SelfRoot is built around the following principles:

- Biometric data remains local to the originating device
- Raw biometric data is never intentionally retained
- Identity verification is based on cryptographic proof
- Private authentication keys remain under user or device control
- Authentication does not require a centralized biometric database
- Core security functions remain auditable and independently testable
- Optional capabilities do not compromise the core security model
- The system is modular and designed to avoid vendor lock-in
- Builds and security-sensitive operations should be reproducible where practical
- The project contains no mandatory telemetry or analytics

---

## Architecture

SelfRoot separates foundational security capabilities from optional integrations.

### Core Modules

Core modules provide the functionality required to establish, protect, and verify a SelfRoot identity.

### Plugin Modules

Plugin modules extend SelfRoot with additional hardware, platforms, authentication methods, protocols, identity systems, and deployment integrations without requiring those capabilities to become dependencies of the core system.

The architecture is intended to allow a minimal SelfRoot deployment to operate with only the components necessary for its intended use.

---

# Core Modules

## Identity Core

The Identity Core manages the fundamental identity model.

### Features

- Deterministic identity creation
- Local identity state
- Identity initialization
- Identity metadata management
- Device and identity binding
- Identity lifecycle management
- Identity rotation
- Identity revocation
- Identity re-rooting
- Public identity representation
- Identity integrity validation

---

## Biometric Core

The Biometric Core provides the local processing framework for biometric authentication.

### Features

- Local biometric capture interface
- Biometric feature processing
- Biometric template generation
- Cancelable biometric representations
- Non-reversible template design
- Volatile-memory processing
- Biometric matching
- Match confidence evaluation
- Sensor abstraction
- Biometric processing policy enforcement
- Raw biometric data disposal

SelfRoot must not treat a biometric template as a replacement for a biometric image. Templates must be designed so that compromise does not provide a practical method for reconstructing the original biometric.

---

## Cryptographic Core

The Cryptographic Core provides the cryptographic primitives and key operations used throughout SelfRoot.

### Features

- Cryptographic key generation
- Public/private key management
- Digital signatures
- Signature verification
- Secure random generation
- Key derivation
- Encryption
- Decryption
- Key rotation
- Key revocation
- Cryptographic identity binding
- Cryptographic integrity verification

SelfRoot should rely on established, independently reviewed cryptographic implementations rather than implementing cryptographic primitives from scratch.

---

## Key Binding Core

The Key Binding Core connects local biometric verification with cryptographic key access.

### Features

- Biometric-to-key binding
- Local private-key unlocking
- Hardware-backed key support
- Key access policy enforcement
- Authentication attempt controls
- Key isolation
- Secure key lifecycle management
- Key replacement
- Identity re-rooting

Biometric processing should authorize access to a cryptographic key rather than treating the biometric itself as a transferable credential.

---

## Authentication Core

The Authentication Core provides the protocol used to prove control of a SelfRoot identity.

### Features

- Challenge generation
- Challenge validation
- Challenge-response authentication
- Digital signature authentication
- Replay protection
- Authentication session management
- Authentication policy enforcement
- Authentication result validation
- Passwordless authentication
- Stateless verification support

The authentication protocol must avoid transmitting biometric information as part of normal authentication.

---

## Verification Core

The Verification Core provides the mechanisms required to verify cryptographic authentication results.

### Features

- Signature verification
- Identity verification
- Challenge validation
- Credential state validation
- Key status validation
- Revocation checking
- Authentication result generation
- Stateless verification
- Offline verification support where configured

The verification layer should require only the information necessary to validate the cryptographic proof.

---

## Secure Storage Core

The Secure Storage Core manages sensitive local state that is required by SelfRoot.

### Features

- Encrypted local storage
- Secure key storage
- Protected identity metadata
- Secure configuration storage
- Credential state management
- Secure deletion
- Storage integrity verification
- Hardware-backed storage integration

Biometric source data must not be persisted as part of normal SelfRoot operation.

---

## Security Policy Core

The Security Policy Core provides centralized enforcement of SelfRoot security requirements.

### Features

- Authentication policies
- Biometric processing policies
- Key access policies
- Device trust policies
- Rate limits
- Attempt limits
- Lockout controls
- Revocation policies
- Recovery policies
- Plugin permission policies
- Security event policies

Plugin modules must operate within the permissions granted by the Security Policy Core.

---

## Audit & Integrity Core

The Audit & Integrity Core provides transparency and security validation capabilities.

### Features

- Cryptographic integrity checks
- Configuration integrity validation
- Component integrity verification
- Security event recording
- Local audit records
- Reproducible build support
- Component version verification
- Dependency integrity tracking
- Security audit tooling

Audit records must not unnecessarily contain biometric information or sensitive authentication material.

---

# Optional Plugin Modules

Plugin modules extend SelfRoot without changing the foundational identity and cryptographic architecture.

Plugins should be independently installable, removable, auditable, and permission-controlled.

---

## Biometric Sensor Plugins

Additional biometric hardware can be supported through dedicated plugins.

### Examples

- Fingerprint sensors
- Facial recognition sensors
- Iris scanners
- Palm recognition sensors
- Hand geometry sensors
- Other compatible biometric hardware

Each sensor plugin must conform to the Biometric Core interface and preserve SelfRoot's local-processing requirements.

---

## Liveness Detection Plugins

Optional liveness detection implementations can provide additional protection against presentation attacks.

### Features

- Passive liveness detection
- Active liveness challenges
- Sensor-specific liveness analysis
- Presentation attack detection
- Configurable confidence thresholds

---

## Hardware Security Plugins

Hardware-specific plugins can integrate SelfRoot with secure key storage and trusted execution environments.

### Examples

- TPM
- Secure Enclave
- Trusted Platform security modules
- Hardware security modules
- Trusted execution environments
- Secure elements

---

## Platform Plugins

Platform plugins provide operating-system-specific functionality.

### Examples

- Linux
- Windows
- macOS
- Android
- iOS
- Embedded Linux
- Specialized embedded platforms

Platform plugins should expose native capabilities through stable SelfRoot interfaces without coupling the core system to a specific operating system.

---

## Authentication Protocol Plugins

SelfRoot can support additional authentication protocols through plugins.

### Examples

- Web authentication
- SSH authentication
- Local workstation authentication
- Enterprise authentication
- Network authentication
- API authentication
- Device-to-device authentication

---

## Identity Protocol Plugins

Optional identity interoperability can be provided through plugins.

### Examples

- Decentralized identity systems
- Verifiable credentials
- Public-key identity systems
- Organization-specific identity protocols
- Federated identity interoperability

Identity protocol plugins must not require centralized storage of biometric information.

---

## Storage Plugins

Alternative secure storage backends can be implemented as plugins.

### Examples

- Operating-system secure storage
- TPM-backed storage
- Secure enclave storage
- Hardware security modules
- Encrypted removable storage
- User-controlled local storage

---

## Verification Service Plugins

Optional plugins can provide integration with external verification environments.

### Examples

- Stateless verification servers
- Local verification services
- Enterprise verification systems
- Offline verification networks
- Peer-to-peer verification
- API gateways

External services should receive cryptographic verification material rather than raw biometric information.

---

## Developer SDK Plugins

SDK plugins can expose SelfRoot functionality to application developers.

### Examples

- Rust SDK
- Web integration SDK
- Mobile SDK
- Desktop SDK
- CLI integration
- API client libraries

---

## Deployment Plugins

Deployment-specific plugins can adapt SelfRoot for different environments.

### Examples

- Enterprise deployments
- Government systems
- Healthcare environments
- Industrial environments
- Educational systems
- Personal devices
- Offline environments
- Air-gapped environments
- Embedded systems

---

# Plugin Requirements

All plugins must:

- Comply with AGPL-3.0+
- Respect SelfRoot security policies
- Declare their permissions and capabilities
- Use documented core interfaces
- Avoid unauthorized biometric data retention
- Avoid unauthorized biometric transmission
- Avoid mandatory telemetry
- Document external dependencies
- Provide appropriate tests
- Document security considerations
- Preserve user control over identity credentials

Security-sensitive plugins should undergo independent review before being recommended for production use.

---

# Security Model

SelfRoot is designed around the separation of biometric presence from cryptographic identity.

The intended authentication flow is:

1. A user presents a biometric locally.
2. The Biometric Core processes the signal.
3. The biometric representation is evaluated locally.
4. Successful verification authorizes access to a cryptographic key.
5. The Authentication Core receives a challenge.
6. The cryptographic key signs the challenge.
7. The verifier validates the signature.
8. Authentication succeeds or fails.

The biometric itself is not transmitted as proof of identity.

---

# Privacy Model

SelfRoot is designed to minimize the information required for authentication.

### Core privacy requirements

- No centralized biometric database
- No raw biometric transmission
- No intentional persistent storage of raw biometric data
- Local biometric processing
- Cryptographic authentication
- User-controlled identity credentials
- No mandatory telemetry
- Minimal verification data
- Configurable local audit information

A deployment must not claim that biometric information is impossible to recover from every implementation without validating the specific biometric algorithm, hardware, template construction, storage architecture, and threat model being used.

---

# Threat Model

Security development should address, at minimum:

- Stolen devices
- Compromised devices
- Lost credentials
- Replay attacks
- Presentation attacks
- Malicious biometric sensors
- Compromised plugins
- Malicious verification services
- Key extraction attempts
- Brute-force attacks
- Unauthorized identity enrollment
- Identity substitution
- Template compromise
- Supply-chain attacks
- Dependency compromise
- Network interception
- Privilege escalation

Threat models should be documented separately for each supported biometric modality and hardware platform.

---

# Development Principles

SelfRoot development should prioritize:

- Memory-safe implementation
- Minimal trusted computing base
- Small security-sensitive components
- Well-established cryptographic libraries
- Explicit interfaces
- Deterministic behavior
- Reproducible builds
- Independent testing
- Security review
- Hardware isolation where available
- Modular architecture
- Vendor-neutral interfaces
- Local-first operation

Rust is the recommended language for security-sensitive core components.

---

# Feature Checklist

## Core Identity
- [ ] Deterministic identity creation
- [ ] Local identity state
- [ ] Device and identity binding
- [ ] Identity lifecycle management
- [ ] Identity rotation
- [ ] Identity revocation
- [ ] Identity re-rooting
- [ ] Identity integrity validation

## Core Biometrics
- [ ] Local biometric capture
- [ ] Biometric feature processing
- [ ] Cancelable biometric representation
- [ ] Non-reversible template design
- [ ] Volatile-memory processing
- [ ] Local biometric matching
- [ ] Sensor abstraction
- [ ] Raw biometric disposal

## Core Cryptography
- [ ] Key generation
- [ ] Key management
- [ ] Digital signatures
- [ ] Signature verification
- [ ] Key derivation
- [ ] Encryption
- [ ] Decryption
- [ ] Key rotation
- [ ] Key revocation

## Core Key Binding
- [ ] Biometric-to-key binding
- [ ] Local private-key unlocking
- [ ] Hardware-backed key support
- [ ] Key isolation
- [ ] Key access policies
- [ ] Identity re-rooting

## Core Authentication
- [ ] Challenge generation
- [ ] Challenge validation
- [ ] Challenge-response authentication
- [ ] Replay protection
- [ ] Passwordless authentication
- [ ] Authentication policy enforcement
- [ ] Session management

## Core Verification
- [ ] Signature verification
- [ ] Identity verification
- [ ] Revocation checking
- [ ] Stateless verification
- [ ] Offline verification
- [ ] Verification result generation

## Core Storage
- [ ] Encrypted local storage
- [ ] Secure key storage
- [ ] Protected identity metadata
- [ ] Secure deletion
- [ ] Storage integrity validation
- [ ] Hardware-backed storage support

## Core Security
- [ ] Security policy engine
- [ ] Rate limiting
- [ ] Attempt controls
- [ ] Lockout controls
- [ ] Plugin permission controls
- [ ] Recovery policies
- [ ] Security event policies

## Core Auditability
- [ ] Integrity verification
- [ ] Configuration validation
- [ ] Component verification
- [ ] Local security event records
- [ ] Reproducible build support
- [ ] Dependency integrity tracking
- [ ] Security audit tooling

## Optional Plugins
- [ ] Fingerprint sensor plugins
- [ ] Facial recognition plugins
- [ ] Iris scanner plugins
- [ ] Palm recognition plugins
- [ ] Liveness detection plugins
- [ ] TPM plugins
- [ ] Secure Enclave plugins
- [ ] Secure element plugins
- [ ] Linux plugin
- [ ] Windows plugin
- [ ] macOS plugin
- [ ] Android plugin
- [ ] iOS plugin
- [ ] Web authentication plugin
- [ ] SSH authentication plugin
- [ ] Enterprise authentication plugin
- [ ] Decentralized identity plugin
- [ ] Verifiable credential plugin
- [ ] External verification plugin
- [ ] Developer SDK plugins
- [ ] Deployment plugins

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
  - [https://roxanneardary.com/selfroot/](https://roxanneardary.com/selfroot//)

---

## License & Notice Requirements

SelfRoot is released under the **GNU Affero General Public License v3.0 or later (AGPL-3.0+)**.   
By contributing to this project, you agree that your contributions will also be released under this license.

Please note the following:

- All contributions must comply with the **AGPL-3.0+** terms.  
- Under **Section 7** of the license, all redistributions, forks, and derivative works must preserve attribution to:  
  **Roxanne Ardary** and **[roxanneardary.com](https://www.roxanneardary.com/)**.
- SelfRoot specificiations are free to use with attribution. A Specification Branding License can be negotiated upon request.
- The project's **notice.md** file tracks attribution requirements and contributor acknowledgments.  
  Any update that adds new contributors or modifies attribution should also update `notice.md`.
- When submitting a pull request, ensure that any new files maintain the attribution headers where applicable.
- Network-deployed versions of this software must also remain fully AGPL-3.0+ compliant, including exposure of source code modifications when applicable under the license.

For full legal details, please refer to the AGPL-3.0+ license and the project's `notice.md` file.
