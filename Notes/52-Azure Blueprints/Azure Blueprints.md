# Azure Blueprints

Azure Blueprints enable **standardized, repeatable environments** across **multiple subscriptions** by packaging artifacts like policies, RBAC, ARM templates, and resource groups into a single definition.

---

## 🔹 Purpose

- Define a **governed environment** configuration.
- Apply consistently across **multiple Azure subscriptions**.
- Maintain **compliance** and enforce organizational standards.

---

## 🔸 Blueprint Artifacts

Blueprints can include:

1. **Resource Groups**
2. **ARM Templates** (Infrastructure as Code)
3. **Role-Based Access Control (RBAC)** Assignments
4. **Azure Policies**

> You can’t have multiple instances of the same artifact within one blueprint.

---

## 🔹 Blueprint Lifecycle

1. **Create a Blueprint Definition**
2. **Publish** a version
3. **Assign** the blueprint to a **subscription**

---

## 🔸 Assignment Locking Options

When assigning a blueprint, you can apply a **lock level**:

| Lock Option    | Behavior                                                            |
|----------------|---------------------------------------------------------------------|
| `Don't Lock`   | Resources can be modified or deleted freely                         |
| `Do Not Delete`| Resources can be changed but **not deleted**                        |
| `Read Only`    | **No changes** to deployed resources allowed via ARM control plane  |

> 🔒 Lock only affects **Azure Resource Manager (ARM)** control plane – **not** the data plane (e.g., blobs in storage).

---

## 🔹 Version Control

- Blueprints support **versioning**.
- Update assignments when a **new version** is published.

---

## 🔸 Enforcement Mechanism

- Enforced using **Deny Assignments**:
  - Prevents even **subscription owners** from overriding settings.
  - Only way to bypass is to:
    - **Unassign** the blueprint, or
    - **Modify the blueprint** itself.

---

## 🔹 Use Case Example (Demo Recap)

Example blueprint includes:

- ✔️ Policy: Apply tag and default value
- ✔️ Resource Group creation
- ✔️ RBAC: Assign Contributor role to a group
- ✔️ ARM Template deployment

> All configured, versioned, and assigned through a **single blueprint** to ensure consistency.

---

## 🔸 Summary

| Feature             | Description                                                |
|---------------------|------------------------------------------------------------|
| Repeatable Setup     | Define reusable configurations for multiple subscriptions |
| Governance           | Apply RBAC, policies, and structure consistently          |
| Lock Levels          | Control what can be changed or deleted post-deployment    |
| Deny Assignments     | Strongest enforcement model to ensure compliance          |

---

## ✅ Ideal For

- **Enterprise-scale governance**
- **Dev/Test environments standardization**
- **Regulatory compliance environments**

