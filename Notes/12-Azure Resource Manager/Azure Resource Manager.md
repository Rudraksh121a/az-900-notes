# Azure Resource Manager (ARM)

Azure Resource Manager is the **management and deployment layer** for Azure. It handles all requests for creating, updating, and deleting resources and enforces policies and permissions.

---

## Why Azure Resource Manager (ARM)?

Before ARM, Azure used **Azure Service Manager**, which had major limitations:
- No granular control over access
- Couldn’t deploy many things in parallel
- Difficult for mass deployment

ARM addresses these issues with:
- Fine-grained access control
- Declarative resource management
- Centralized governance

---

## Resource Providers

Azure is built using **Resource Providers**:
- Each provider offers different types of resources.
- Example: `Microsoft.Compute` provides virtual machines, disks, snapshots, etc.

You can list all available providers using the CLI:
```bash
az provider list
