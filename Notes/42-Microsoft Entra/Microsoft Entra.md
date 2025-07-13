# Microsoft Entra Overview

## Introduction

**Microsoft Entra** is a unified suite of identity-related solutions by Microsoft. It brings together various identity, access, and governance services under a single umbrella — accessible via the [Entra Admin Center](https://entra.microsoft.com).

---

## Components of Microsoft Entra

### 1. **Azure Active Directory (Azure AD)**
- Core identity provider (no changes in functionality).
- Manages **users**, **devices**, **applications**.
- Supports:
  - **Authentication & Single Sign-On (SSO)**
  - **Conditional Access**
  - **Role-Based Access Control (RBAC)**

---

### 2. **Verified ID**
- Enables **decentralized identity management**.
- Built around **verifiable credentials**:
  - Issued by trusted institutions (e.g., employers, governments).
  - Stored in the user's wallet (e.g., Microsoft Authenticator).
  - Shared through **verifiable presentations**, under user control.
- Based on **trust systems** (e.g., blockchain, or other ledgers).

---

### 3. **Permissions Management**
- Based on Microsoft’s acquisition of **CloudKnox**.
- Provides **multi-cloud permission visibility** (Azure, AWS, GCP).
- Key features:
  - Inventory existing permissions.
  - Detect unused or risky permissions.
  - Right-size access by creating custom roles.
  - On-demand privilege elevation support.

---

### 4. **Workload Identities**
- Manages identities for **apps and services** (e.g., service principals, managed identities).
- Extends identity protection to non-human actors.
- Includes:
  - Conditional Access
  - Identity Protection
  - Access Reviews
  - Logging & Monitoring

---

### 5. **Identity Governance**

#### a. **Entitlement Management**
- Create **Access Packages** for group membership, app access, SharePoint, etc.
- Include approvals, request workflows, and time-bound access.

#### b. **Access Reviews**
- Periodically review access rights.
- Users can **self-review** or delegate reviews.

#### c. **Privileged Identity Management (PIM)**
- Just-in-time role elevation for Azure resources and Azure AD roles.

#### d. **Lifecycle Workflows**
- Automates tasks based on user lifecycle events:
  - **Joiner, Mover, Leaver** scenarios.
- Pre-configured workflows for:
  - Pre-hire
  - Onboarding
  - Termination
  - Offboarding / Post-offboarding
- Tasks triggered X days before/after a lifecycle event.

---

## Summary

**Microsoft Entra** is a comprehensive identity and access management suite that includes:
- Centralized identity (Azure AD)
- Decentralized identity (Verified ID)
- Cloud permissions management
- Secure workload identities
- Full identity governance lifecycle

It empowers organizations to manage identity, protect access, and ensure compliance across their cloud environments and applications.

