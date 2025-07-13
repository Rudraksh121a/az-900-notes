# Azure Key Vault

## Lesson Objective
Understand the purpose and functionality of **Azure Key Vault**, including its role in storing and managing **secrets, keys, and certificates**, and how it integrates with access control and identity in Azure.

---

## Topics Covered
- What is Azure Key Vault?
- Types of supported data:
  - Secrets
  - Keys
  - Certificates
- Key Vault architecture and HSM integration
- Access control mechanisms:
  - Access Policies
  - Role-Based Access Control (RBAC)
- Integration with Managed Identity
- Real-world use cases
- Bring Your Own Key (BYOK) scenarios

---

## What is Azure Key Vault?

Azure Key Vault is a **centralized cloud service** that allows secure storage and management of:

- **Secrets** (e.g., passwords, tokens, connection strings)
- **Keys** (e.g., cryptographic keys for encryption)
- **Certificates** (e.g., SSL/TLS certificates)

It eliminates the need to hardcode sensitive values in your application code, making applications more secure.

---

## Supported Data Types

### 1. Secrets
- Can be **created**, **read**, **updated**, and **deleted**.
- Examples: API keys, passwords, tokens.

### 2. Keys
- Can be **generated** or **imported**.
- Supports cryptographic operations like encrypt/decrypt, sign/verify.
- **Keys cannot be exported** from the Key Vault.
- Used internally by the application via Key Vault APIs.

### 3. Certificates
- Helps in **lifecycle management**:
  - Creation
  - Renewal
  - Distribution
- Built-in support for **integrating with certificate authorities**.

---

## Hardware Security Modules (HSMs)

- Azure Key Vault supports **HSM-backed keys** for higher security.
- HSMs are specialized hardware designed for **secure storage and key operations**.

---

## Access Control in Key Vault

### 1. Access Policies (Legacy)
- Assigns permissions at the **vault level**.
- Supports granting access to:
  - Secrets
  - Keys
  - Certificates
- **Not granular** — access applies to all items of that type.
- To isolate access, you would need to **create multiple Key Vaults**.

### 2. Role-Based Access Control (RBAC)
- **Preferred method** for new deployments.
- Provides **fine-grained access** at individual secret, key, or certificate levels.
- Uses built-in roles like:
  - `Key Vault Reader`
  - `Key Vault Secrets User`
  - `Key Vault Contributor`

### RBAC Example:
- Secret 1: Accessible by Clark Kent.
- Secret 2: Accessible by Bruce Wayne.

This demonstrates how **different users can be given access to different secrets** in the same vault.

---

## Integration with Managed Identity

- Managed Identity provides an automatically managed identity for Azure resources (like App Service, VM).
- This identity can be granted access to Key Vault.
- Enables **secure, passwordless access** to secrets for Azure-hosted applications.

### Example:
- App Service has a system-assigned managed identity.
- Grant this identity access to a specific secret via RBAC.
- App can now securely retrieve the secret at runtime without storing credentials.

---

## Bring Your Own Key (BYOK)

Azure services like:
- **Storage Accounts**
- **SQL Database**
- **Azure Disk Encryption**

...can use **your own encryption keys** stored in Key Vault.

Benefits:
- **Full control** over key lifecycle (rotation, revocation).
- Meets **compliance** and **data sovereignty** requirements.

---

## Summary Table

| Feature                      | Description                                               |
|------------------------------|-----------------------------------------------------------|
| Secrets                      | Store sensitive data like passwords and tokens           |
| Keys                         | Perform cryptographic operations using protected keys     |
| Certificates                 | Manage and auto-renew SSL/TLS certificates               |
| Access Policies              | Legacy access control model with broad permissions        |
| Role-Based Access Control    | Granular, modern access control at item level             |
| Managed Identity             | Secure identity for Azure services to access the vault    |
| HSM Support                  | Use hardware-based protection for high-security keys      |
| BYOK                         | Use your own keys for encryption in Azure services        |

---

