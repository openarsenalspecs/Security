# PrivyKey

**The Open Way to Safe Logins**

PrivyKey is a fully open-source, privacy-first, encrypted authentication system designed to replace closed-source 2FA apps. It provides secure, local-first time-based authentication with a modular, future-proof architecture built for extensibility, auditability, and zero-knowledge security.

---

## 🔐 Overview

PrivyKey is a next-generation authenticator that gives users full control over their authentication keys. It is designed around a strict security model where secrets are never exposed in plaintext outside secure memory boundaries and are always encrypted at rest.

The system is built to evolve beyond traditional 2FA into a full identity and authentication platform while remaining fully open-source and auditable.

---

## ✨ Key Features

### 🔑 Authentication
- Full TOTP support (RFC 6238 compliant)
- HOTP support (RFC 4226 optional compatibility)
- Multi-account authentication storage
- Offline code generation (no internet required)
- Time drift tolerance with secure validation windows

---

### 🔐 Encrypted Vault System
- Fully encrypted local key vault
- Zero plaintext storage of secrets
- Per-account encryption isolation
- Vault locking and unlocking system
- Secure cryptographic wipe on deletion

---

### 🧠 Cryptographic Security
- AES-256-GCM encryption (primary standard)
- ChaCha20-Poly1305 support (performance alternative)
- Argon2id key derivation (memory-hard protection)
- Secure random generation using OS-level entropy sources
- Constant-time verification to reduce timing attack risk

---

### 📷 Account Setup & QR System
- QR code scanning for instant onboarding
- `otpauth://` URI compatibility
- Manual secret entry support
- Secure QR parsing and validation pipeline

---

### 🔄 Backup & Recovery
- Encrypted offline backup export
- QR-based backup encoding
- Optional self-hosted encrypted sync support (zero-knowledge design)
- User-controlled recovery mechanisms

---

### 🛡️ Security Architecture
- Zero-knowledge design (system cannot read secrets in plaintext)
- Secure memory handling with explicit zeroization
- Vault auto-lock on inactivity timeout
- Brute-force mitigation with progressive delays
- Optional biometric vault unlocking (device dependent)

---

### 📱 Platform Support
- Android (Kotlin + Jetpack Compose)
- iOS (Swift + SwiftUI)
- Future: Web / PWA support
- Modular architecture for cross-platform expansion

---

### ⚙️ Modular Architecture
PrivyKey is designed as a fully modular system:

- UI Layer (fully replaceable)
- Application Logic Layer (event-driven orchestration)
- Cryptography Core (swappable security engine)
- Vault Storage Layer (pluggable encrypted storage backends)
- Protocol Layer (TOTP, QR, import/export systems)
- Sync Layer (optional zero-knowledge encrypted sync)
- Security Governance Layer (integrity, validation, and auditing)

Each module is independently testable and replaceable without affecting system integrity.

---

### 🌐 Open Standards & Compatibility
- Full TOTP / HOTP interoperability
- Standard QR provisioning format support
- Compatible with existing authenticator ecosystems
- Extensible authentication protocol framework (future WebAuthn support planned)

---

### 🚀 Future Enhancements
- FIDO2 / WebAuthn support (hardware key integration)
- Post-quantum cryptography module support (experimental)
- Encrypted multi-device synchronization (zero-knowledge mesh)
- Self-hosted identity vault server
- Enterprise authentication policy layer
- Plugin-based security module ecosystem

---

## 🧱 Architecture Philosophy

PrivyKey is built on three core principles:

- **User Ownership:** Users fully control their keys and authentication data
- **Zero Trust by Default:** No system component is trusted without verification
- **Modularity First:** Every component can be replaced, upgraded, or audited independently

---

## 📌 Contributing

Contributions are welcome. Please ensure all contributions follow the security, encryption, and modular architecture standards defined in this repository.

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
  - [https://roxanneardary.com/privykey/](https://roxanneardary.com/privykey/)

---

## 🧾 License & Notice Requirements

PrivyKey is released under the **GNU Affero General Public License v3.0 or later (AGPL-3.0+)**.   
By contributing to this project, you agree that your contributions will also be released under this license.

Please note the following:

- All contributions must comply with the **AGPL-3.0+** terms.  
- Under **Section 7** of the license, all redistributions, forks, and derivative works must preserve attribution to:  
  **Roxanne Ardary** and **[roxanneardary.com](https://www.roxanneardary.com/)**.
- PrivyKey specifications are free to use with attribution. A Specification Branding License can be negotiated upon request.
- The project's **notice.md** file tracks attribution requirements and contributor acknowledgments.  
  Any update that adds new contributors or modifies attribution should also update `notice.md`.
- When submitting a pull request, ensure that any new files maintain the attribution headers where applicable.
- Network-deployed versions of this software must also remain fully AGPL-3.0+ compliant, including exposure of source code modifications when applicable under the license.

For full legal details, please refer to the AGPL-3.0+ license and the project's `notice.md` file.
