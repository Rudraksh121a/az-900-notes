# Describing External Identities in Microsoft Entra

This lesson explores how to securely collaborate with **external users** in Microsoft Entra, through models like **Business-to-Business (B2B)**, **Business-to-Customer (B2C)**, and **B2B Direct**.

---

## Internal vs External Identities

### Internal Identities
- Created directly in **Entra ID**
- Or synced from **Active Directory (AD DS)** using:
    - **Entra Connect Sync**
    - **Entra Cloud Sync**

### External Identities
Used for users **outside your organization**, typically:
- **Partners (B2B)**
- **Customers (B2C)**

---

## Business-to-Business (B2B)

### Purpose:
Enable collaboration with **partners** from other organizations.

### Key Characteristics:
- Partners **use their home identity provider**
- They are represented in your Entra tenant as **guest users (stub objects)**
- Still governed by **Conditional Access** policies

### Supported Identity Providers:
- Other **Entra tenants**
- **Microsoft Accounts**
- **Google** or **Facebook**
- **One-time passcode** via email
- **SAML** / **WS-Fed** (custom federations)

### Provisioning Options:
- Manual **invitation**
- **Entitlement Management**
- **Self-service** onboarding flows

### Security:
- External users still go through **Conditional Access**
- You can enforce **MFA**, device compliance, etc.

---

## B2B Direct (for Microsoft Teams)

### Purpose:
Used **only for Microsoft Teams collaboration**, including:
- Shared channels
- Messaging across orgs

### Features:
- No need to create guest user objects
- Users remain in their **own organization**
- Simplified **cross-org collaboration**

---

## Business-to-Customer (B2C)

### Purpose:
For exposing applications to **millions of end-users** (e.g., customers).

### Key Characteristics:
- Completely separate **B2C tenant**
- Highly customizable sign-in and branding
- Supports a wide range of **social identities**

### Supported Identity Providers:
- **Facebook**
- **Google**
- **Amazon**
- **Apple**
- **Twitter**
- **WeChat**
- **Local accounts** (custom email/password)

### Customization:
- **Customize every pixel**
- Support for **branding, onboarding flows, user attributes**
- Designed for **public-facing apps**

---

## Summary Table

| Category    | Use Case               | User Type       | Where Managed | Auth Method           | Customization     |
|-------------|------------------------|------------------|---------------|------------------------|-------------------|
| **B2B**     | External partners       | Guest users      | Corporate tenant | Home ID + Conditional Access | Minimal        |
| **B2B Direct** | Teams shared channels | External contacts | Their own org    | Home ID                | Minimal        |
| **B2C**     | Public-facing apps      | Customers        | Separate tenant | Social/local ID        | Full branding   |

---

## Key Takeaways

- Do **not** create direct accounts in your tenant for external users.
- Use **B2B** for partners, **B2B Direct** for Teams sharing, and **B2C** for customers.
- Leverage **federation**, **identity providers**, and **conditional access** to manage access securely.

---

This completes the lesson on **Describing External Identities in Mic**
