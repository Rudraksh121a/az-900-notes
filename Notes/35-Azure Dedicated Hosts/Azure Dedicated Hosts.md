# Azure Dedicated Hosts

## Overview
Azure Dedicated Hosts provide **physical servers** dedicated to your organization. You get control over host-level resources, including **hardware isolation**, **licensing benefits**, and **maintenance scheduling**.

---

## Why Use Dedicated Hosts?

- **Isolation**: Only your VMs are placed on the physical host—no multi-tenancy.
- **Compliance**: Meets strict regulatory or security requirements.
- **Licensing**: You can reuse existing software licenses (e.g., Windows Server, SQL Server).
- **Maintenance Control**: Define custom **maintenance windows** (rolling 35-day period).

---

## Key Concepts

### 1. **Multi-Tenancy in Azure (Default)**
- VMs from multiple tenants share physical servers.
- Isolation is ensured via hypervisors and SDN.

### 2. **Dedicated Hosts**
- Entire physical server allocated to a single customer (your tenant).
- No other VMs from other tenants share the same host.

---

## Architecture

### Region ➝ Availability Zone (Optional) ➝ Host Group ➝ Hosts ➝ VMs

1. **Host Group**
   - Logical grouping of dedicated hosts within a region or AZ.

2. **Dedicated Host**
   - A specific physical server (SKU-based) added to the host group.
   - Can be distributed across different **fault domains** (i.e., different racks).

3. **VM Placement**
   - VMs are assigned to specific hosts or host groups.
   - Only your VMs can run on the host.

---

## Host SKUs and VM Compatibility

- Each **Dedicated Host SKU** supports only a specific **VM family**.
- Example: A `DASv4` host supports only `DASv4` VMs.
- VMs of different sizes **within the same family** can be placed on the same host.

### Example:
| Host SKU   | Allowed VM Types           |
|------------|-----------------------------|
| `DASv4`    | `D2as_v4`, `D4as_v4`, etc.   |
| `ESv4`     | `E2s_v4`, `E4s_v4`, etc.     |

---

## Isolated VM Sizes

- Special **VM sizes** so large that they occupy the **entire host**.
- No need for a dedicated host group.
- Azure guarantees no other tenants share the hardware.

### Examples:
- `M128ms`, `M416ms`, `GS5`, etc.

> These VMs **automatically get hardware isolation** due to their size.

---

## Maintenance Control

- For both **Dedicated Hosts** and **Isolated VMs**, you can:
  - Set **maintenance control windows**.
  - Choose when host updates/restarts happen.

---

## Summary Table

| Feature                    | Azure Dedicated Host                        | Isolated VM Size                         |
|----------------------------|---------------------------------------------|------------------------------------------|
| Hardware Isolation         | ✅ Full host isolation                      | ✅ Due to VM size                         |
| Host Group Required        | ✅ Yes                                       | ❌ No                                     |
| Control Over Maintenance   | ✅ Yes                                       | ✅ Yes                                    |
| VM Family Restriction      | ✅ Only one VM family per host              | ✅ One VM occupies full host              |
| Use Case                   | Regulatory compliance, licensing control    | High-performance, massive workloads      |

---

## Tips for AZ-900

- **Azure Dedicated Host** = Physical server for your exclusive use.
- You manage: **VM placement**, **host group**, and **host SKU**.
- **Isolated VMs** don’t need host groups but offer similar benefits.
- Used for **compliance**, **security**, and **licensing** scenarios.
- Supports **Azure Hybrid Benefit** for cost savings.

---


