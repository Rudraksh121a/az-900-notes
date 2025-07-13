# Azure Resource Locks

This lesson explains the purpose, types, and behavior of **Resource Locks** in Microsoft Azure, which act as an extra safeguard beyond RBAC to prevent accidental deletion or modification of critical resources.

---

## 1. What Are Resource Locks?

- A **Resource Lock** prevents accidental changes or deletions of Azure resources.
- It applies an extra layer of protection at the **Azure Resource Manager (ARM) control plane**.
- It does **not** affect the **data plane** (i.e., the actual data within the resource).

---

## 2. Scope of Locks

- Locks can be applied at different hierarchical levels:
  - Subscription
  - Resource Group
  - Resource
- Locks are **inherited** down the hierarchy:
  - A lock at the subscription level affects all resource groups and resources within it.
  - A lock at the resource group level affects all resources inside that group.

---

## 3. Types of Resource Locks

1. **CanNotDelete**
   - Allows modifications
   - Prevents deletion of the resource

2. **ReadOnly**
   - Prevents both modifications and deletions
   - Only read actions are allowed

---

## 4. Control Plane vs. Data Plane

- Locks apply only to the **control plane** (ARM):
  - Example: Prevents deleting a storage account or VM
- Locks do **not** impact the **data plane**:
  - Example: You can still delete blobs or update database records inside the resource

---

## 5. Permissions Required

- To create or remove a lock, the user must be:
  - **Owner** of the resource scope
  - Or a **User Access Administrator** (rare, elevated role)

---

## 6. Usage Behavior

- Applying a lock:
  - Must be done by an authorized identity at the desired scope
  - Visible in the portal under the **Locks** section
- Removing a lock:
  - Must be done manually
  - Required before the resource can be deleted or modified (depending on lock type)

---

## 7. Example Scenarios

- A storage account has a **CanNotDelete** lock:
  - You can read/write blobs
  - You **cannot delete** the storage account without first removing the lock

- A resource group has a **ReadOnly** lock:
  - You can view resources
  - You **cannot update or delete** any resource within that group

---

## 8. Best Practices

- Use locks on:
  - Mission-critical resources
  - Shared infrastructure (e.g., VNets, storage, production databases)
- Combine with RBAC to ensure least privilege
- Document lock usage to avoid confusion among admin teams

---

## 9. Summary Table

| Lock Type     | Allows Read | Allows Modify | Allows Delete | Common Use Case                        |
|---------------|-------------|----------------|----------------|----------------------------------------|
| CanNotDelete  | Yes         | Yes            | No             | Prevent accidental deletions           |
| ReadOnly      | Yes         | No             | No             | Freeze configuration for critical resources |

---

## 10. Key Takeaways

- **Resource Locks** enforce intentional management actions
- They apply at the **control plane**, not the data layer
- Locks must be **explicitly removed** to perform restricted actions
- Always consider **inheritance** when managing locks at higher scopes

---

This concludes the lesson on **Resource Locks in Azure**.
