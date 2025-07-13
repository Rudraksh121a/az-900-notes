# Role-Based Access Control (RBAC) in Microsoft Azure

This lesson covers the functionality, structure, and usage of **RBAC**—a fundamental governance feature in Azure used to manage permissions across resources.

---

## What is RBAC?

RBAC allows administrators to grant users the **minimum permissions** required to perform their tasks. It is built around assigning **roles** to **identities** at a specific **scope**.

---

## Key Components of RBAC

1. **Identity**:
   - User
   - Group
   - Service Principal
   - Managed Identity

2. **Role**:
   - A set of permissions (actions) that define what operations the identity can perform.

3. **Scope**:
   - Management Group
   - Subscription
   - Resource Group
   - Resource

4. **Role Assignment**:
   - A combination of the above three (Identity + Role + Scope).

---

## How RBAC Works

- Permissions are **inherited** down the resource hierarchy:
  - From Management Group → Subscription → Resource Group → Resource
- Role assignments are **additive**:
  - If a user is assigned roles at multiple levels, all permissions are combined.
- There is **no default deny** in RBAC (except for specific use cases like Blueprints).

---

## Common Built-in Roles

| Role         | Description                                                       |
|--------------|-------------------------------------------------------------------|
| Owner        | Full access, including permission management                      |
| Contributor  | Full access to manage resources, but cannot assign permissions    |
| Reader       | Read-only access to resources                                     |

Other roles are more specialized (e.g., **Virtual Machine Contributor**, **Network Contributor**).

---

## Role Assignment Process

1. Choose the **role** (e.g., Reader, Contributor).
2. Select the **identity** (user, group, service principal).
3. Choose the **scope** (e.g., Subscription).

Once assigned:
- Permissions flow down from the assigned scope.
- Visible in **Access Control (IAM)** of each resource.

---

## Enforced by Azure Resource Manager (ARM)

- All access passes through the **ARM control plane**.
- There is **no bypass** for APIs, PowerShell, CLI, or portal.
- RBAC is **centrally and consistently enforced**.

---

## Real-world Example

- A user is assigned **Reader** at the **subscription** level.
  - They can view resources in all resource groups and services.
- Another user is assigned **Virtual Machine Contributor** at the **resource group** level.
  - They can manage only virtual machines within that group.

---

## Inheritance & Scope Visualization

