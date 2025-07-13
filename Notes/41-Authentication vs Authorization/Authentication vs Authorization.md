# Azure Identity: Authentication vs Authorization

## Topics Covered
- Difference between authentication and authorization
- Concepts of AuthN and AuthZ
- Identity verification methods
- Role-Based Access Control (RBAC) in Azure

---

## 1. Introduction

This lesson introduces the key concepts of **Authentication** and **Authorization** within the Azure identity ecosystem. These are foundational for understanding identity governance, privacy, and compliance in Azure.

---

## 2. What is Authentication (AuthN)?

**Authentication** is the process of **verifying the identity** of a user or service.  
It's about proving **"Who you are."**

### Authentication Methods:
- **Something you know**: Password, PIN
- **Something you have**: Token, device, smartcard
- **Something you are**: Biometric (fingerprint, face, iris)

> Example: Windows Hello uses TPM (Trusted Platform Module) with PIN or biometrics.

---

## 3. What is Authorization (AuthZ)?

**Authorization** determines **what actions** an authenticated identity is allowed to perform.  
It's about answering **"What can you do?"**

### In Azure:
- Implemented via **Role-Based Access Control (RBAC)**
- Access is granted to **roles** at specific **scopes** (subscription, resource group, resource)

---

## 4. Auth Flow Summary

1. **Authenticate** → Prove your identity  
2. **Authorize** → Get permissions for what you’re allowed to access

---

## 5. Common Abbreviations
- **AuthN**: Authentication
- **AuthZ**: Authorization

---

## 6. Real-world Example

When logging into Azure Portal:
- **Authentication** checks your username/password or biometric/token.
- **Authorization** checks whether you can read resources, modify VMs, or access storage based on your role.

---

