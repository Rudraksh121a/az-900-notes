# Azure Network Security: Defense in Depth

##  What is Defense in Depth?
Defense in Depth is a **layered security strategy**. It ensures that if one security layer is compromised, others still protect the system. Just like a castle has **moats, gates, and walls**, Azure security uses **multiple protection layers**.

---

##  Security Layers (from inside out)

### 1. **Data (Core Asset)**
- Most valuable asset.
- Protect using:
  - **Data encryption (at rest & in transit)**
  - **Data classification** to apply the right security measures.

### 2. **Application**
- Ensure secure development:
  - No secrets in code (use **Azure Key Vault**).
  - Apply **Web Application Firewall (WAF)**.
  - Patch vulnerabilities and use secure coding best practices.

### 3. **Compute**
- Secure VMs, containers, and services:
  - **OS patching**, **anti-malware**, and **firewalls**.
  - Use **Microsoft Defender for Cloud** for threat detection.
  - In PaaS, Azure handles most of this.

### 4. **Network**
- Apply **Zero Trust** and **least privilege** principles.
- Use:
  - **Network Security Groups (NSG)**
  - **Private Endpoints**
  - **Load Balancers** and **Application Gateways**
  - **Deny by default**
  - Encrypted connections (e.g., VPN, ExpressRoute)

### 5. **Perimeter**
- Protect at the edge:
  - **Azure DDoS Protection** to prevent large-scale attacks.
  - **Edge firewalls** filter traffic before entering internal networks.

### 6. **Identity & Access**
- **Identity is the new perimeter** in cloud.
- Use:
  - **Multi-Factor Authentication (MFA)**
  - **Passwordless login**
  - **Azure AD Conditional Access**
  - **Audit logs and identity governance**
  - Apply **Zero Trust**: verify explicitly, never trust by default.

### 7. **Physical Security**
- Managed by **Microsoft** in Azure data centers:
  - Surveillance, biometric access, guards, etc.

---

## Shared Responsibility Model
| Service Model | Your Responsibility | Azure Responsibility |
|---------------|---------------------|----------------------|
| **IaaS**      | Most layers          | Physical & infra     |
| **PaaS**      | App & data           | Infra + compute      |
| **SaaS**      | Identity & access    | Everything else      |

---

## CIA Triad (Core Security Principles)

| Principle         | Description                                                        |
|------------------|--------------------------------------------------------------------|
| **Confidentiality** | Limit access to only authorized users (Least Privilege)         |
| **Integrity**        | Ensure data is not altered (Signatures, Hashing, Encryption)   |
| **Availability**     | Ensure services are always accessible (DDoS Protection, Redundancy) |

---

## Summary

- Defense in depth = **Multiple layers of protection**.
- Key components include: **App security**, **network rules**, **identity management**, and **DDoS protection**.
- **CIA triad** ensures data is secure, accurate, and accessible.
- Aligns with **Zero Trust** and **Shared Responsibility** principles.

---

## Quick AZ-900 Tips

- **Defense in Depth** ≠ single firewall or NSG.
- Think **multiple layers**: identity, network, compute, app, data, perimeter.
- Understand **Zero Trust** and **least privilege access**.
- **MFA**, **encryption**, and **private networking** are core components.
- Azure handles **physical security**, you handle **identity & configuration**.

---

