# Azure Network Security: Zero Trust

## What is Zero Trust?

Zero Trust is a security model based on the principle that **no device, user, or service** should be trusted by default — even if it is inside the organization's network.

It builds on **Defense in Depth** by assuming **every request is potentially hostile** and enforces strict verification.

---

## Core Principles of Zero Trust

### 1. Verify Explicitly
- **Revalidate identity, device health, and context** for every request.
- Applies to users, devices, and services (e.g., service principals).
- Use real-time signals and risk detection.

### 2. Least Privilege Access
- Grant **only the minimum permissions** necessary to perform a task.
- Use **Just-in-Time (JIT)** access via tools like **Privileged Identity Management (PIM)**.
- Enforce **Role-Based Access Control (RBAC)** to manage permissions effectively.

### 3. Assume Breach
- Always expect that the network, device, or process may be compromised.
- Monitor continuously using telemetry and automation.
- Treat internal network like the internet — apply the same scrutiny.

---

## Key Components of Zero Trust

### Identity
- Users, service principals, managed identities.
- Ensure secure identity with:
  - Multi-Factor Authentication (MFA)
  - Passwordless authentication
  - Identity protection and risk assessment
  - Single Sign-On (SSO)

### Device/Endpoint
- Devices include laptops, phones, servers, IoT, etc.
- Validate:
  - Health status (patched, not jailbroken)
  - TPM availability
  - Certificates and registration
  - Managed via tools like **Microsoft Defender for Endpoint**

### Network
- Use micro-segmentation and encrypted communication (TLS/IPSec).
- Apply consistent controls for both internal and external networks.
- Enforce least privilege and deny-by-default networking.

### Context
- Analyze:
  - Identity risk
  - Device health
  - Location (network origin)
  - Session behavior
- Combine all this to determine risk and appropriate access level.

### Conditional Access
- Feature in **Azure AD Premium**.
- Grants or blocks access based on real-time conditions.
- Uses context signals to enforce control policies.

### Infrastructure
- Secure and resilient infrastructure (e.g., Gen2 VMs).
- Ensure OS patching, configuration hardening, and secure compute environments.

### Applications and Data
- Know where your data is and how it is classified.
- Apply controls like:
  - Data masking
  - Encryption
  - Monitoring abnormal usage patterns (e.g., mass downloads)
- Grant **access only through secure applications** with appropriate policy controls.

---

## End-to-End Flow in Zero Trust

1. A user or service initiates a request.
2. Identity is verified explicitly (e.g., via MFA).
3. Device health and network origin are validated.
4. Context is gathered and analyzed.
5. Conditional Access evaluates the request.
6. Based on policy, access is granted to data or application.
7. Signals are continuously monitored and can trigger automated responses.

---

## Monitoring & Response

- Use tools like **Microsoft Sentinel** (SIEM/SOAR) to:
  - Collect telemetry
  - Analyze threats
  - Automate responses to detected risks

---

## Summary

| Principle         | Description                                                      |
|------------------|------------------------------------------------------------------|
| **Verify Explicitly** | Always authenticate and validate the context of every request. |
| **Least Privilege**   | Grant minimal access needed and use JIT/PIM for elevation.     |
| **Assume Breach**     | Continuously monitor and expect compromise at any point.       |

Zero Trust is not a product — it's a mindset and architecture model focused on **continuous verification**, **context-aware policies**, and **minimal trust** even inside the network.

