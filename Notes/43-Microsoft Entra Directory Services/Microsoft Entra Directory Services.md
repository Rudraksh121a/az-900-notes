# Microsoft Entra Directory Services

## Overview

Microsoft Entra Directory Services includes:
- **Entra ID** (formerly **Azure Active Directory**)
- **Entra Domain Services** (managed legacy-compatible AD)

---

## History and Terminology

- **Entra ID** = previously **Azure AD**
- **Entra Tenant** = previously **Azure AD Tenant**

---

## On-Premises: Active Directory Domain Services (AD DS)

- Provided by **Windows Server**
- Centralized **identity & access management**
- Key features:
    - **Users, Groups, Computers** stored in shared DB
    - Supports **Single Sign-On (SSO)** within domain
    - Built around **Organizational Units (OUs)** with delegation and Group Policies
    - Communication uses protocols like:
        - **NTLM**, **Kerberos** (for authentication)
        - **LDAP** (for directory access)
        - **DNS** (to locate DCs)

---

## Cloud: Microsoft Entra ID

- **Cloud-native identity provider**
- Communicates using modern protocols:
    - **OpenID Connect**
    - **SAML**
    - **WS-Fed**
- Applications (Microsoft 365, Azure, Dynamics, third-party SaaS) **trust the Entra tenant** for auth.
- Enables:
    - **Federation** with external apps
    - **Conditional Access** policies
    - **Device registration/joining**
    - **Mobile Device Management (MDM)** integration (e.g., Intune)

---

## Integration with On-Premises AD

To sync identities from AD DS to Entra ID:
- Use **Entra Connect** technologies:
    - **Entra Connect Sync** (traditional on-prem engine)
    - **Entra Cloud Sync** (cloud-based engine with lightweight agent on DCs)
- Both replicate users from AD DS to Entra for a seamless SSO experience.

---

## Microsoft Entra Domain Services (Entra DS)

- **Managed Active Directory domain** in Azure.
- Use when:
    - Legacy apps need **NTLM, Kerberos, or LDAP** in cloud
    - You **don’t want** or **can’t connect** to on-premises AD

### Features:
- Syncs from Entra ID into Entra Domain Services
- Deploys **two managed domain controllers** per region (replica set)
- You **don’t manage the DCs**
- Supports **Kerberos, NTLM, LDAP** for legacy compatibility
- Supports up to **5 replica sets** in different regions (with VNet peering)
- Highly restricted — **no Enterprise/domain admin access**

---

## Secure Hybrid/Cloud Access

- **Entra Private Access**: Secure access to private resources in on-prem networks
- **Entra Internet Access**: Controls access to public websites

---

## Summary

| Feature                        | AD DS (On-Prem)         | Entra ID (Cloud)           | Entra Domain Services (Cloud AD) |
|-------------------------------|--------------------------|-----------------------------|----------------------------------|
| Protocols                     | Kerberos, NTLM, LDAP     | SAML, OIDC, WS-Fed          | Kerberos, NTLM, LDAP             |
| Management                    | You manage everything     | Microsoft managed           | Microsoft managed                |
| Use Case                      | Legacy, On-prem systems   | Cloud-native apps           | Legacy apps in cloud             |
| Admin Access                  | Full (Enterprise Admin)   | Admin via Entra Portal      | Limited, no access to DCs        |
| Sync Support                  | N/A                      | From AD via Entra Connect   | From Entra ID                    |

---

## Additional Notes

- Entra provides modern identity and access capabilities while retaining support for legacy systems.
- Enables hybrid identity architectures with **secure synchronization and compatibility**.
- Ideal for companies transitioning to the cloud but still using legacy systems.

