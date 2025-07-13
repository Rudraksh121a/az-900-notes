# Azure Management Hierarchy

Azure provides a **management hierarchy** to organize, manage, and govern resources at scale across large environments.

---

## 1. Top-Level: Azure Active Directory (Azure AD)

- **Identity provider** for all Azure services.
- Contains:
  - Users
  - Groups
  - Service principals
  - Managed identities
- May sync with **on-prem Active Directory** using:
  - Azure AD Connect
  - Azure AD Connect Cloud Sync

---

## 2. Root Management Group

- Automatically created and tied to **Azure AD tenant**.
- Allows **organization-wide governance**.

---

## 3. Management Groups

- Used to **group subscriptions** for unified policy and RBAC.
- Supports up to **6 levels of depth** (excluding root).
- Hierarchical, supports **inheritance**.

---

## 4. Subscriptions

- Logical container for:
  - Resource groups
  - Billing boundary
  - Quota management
- Can’t nest subscriptions.
- Must belong to a single **management group**.

---

## 5. Resource Groups

- Logical containers for resources like VMs, storage, etc.
- Resources in the same group:
  - Share the **same lifecycle** (create, manage, delete).
  - Cannot be nested.

---

## 6. Resources

- Individual services like VMs, web apps, disks, etc.
- Must reside in **one resource group**.

---

## Hierarchy Diagram

```plaintext
Azure AD
 └── Root Management Group
      └── Management Groups (up to 6 levels)
           └── Subscriptions
                └── Resource Groups
                     └── Resources
