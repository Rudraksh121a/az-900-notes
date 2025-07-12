# Virtual Machine: Required Resources

A virtual machine (VM) in Azure is more than just a single resource — it’s part of a **collection of interconnected Azure resources** that enable it to function correctly and securely.

---

## Core Components

### 1. **Virtual Machine (VM)**
- The primary compute resource.
- Defined by size/SKU (e.g., D2s_v3).
- Lives in:
  - A **Subscription**
  - A **Resource Group**
  - A specific **Region**

---

## Storage Resources

### 2. **Operating System Disk**
- Usually a **Managed Disk**.
- Required to boot the OS.
- Charged separately from the VM.

### 3. **Ephemeral OS Disk** *(Optional)*
- Uses host’s temporary/cache storage.
- **Stateless** – lost on deallocation.
- Ideal for stateless workloads like:
  - AKS worker nodes
  - VM Scale Sets

### 4. **Data Disks** *(Optional)*
- For storing app or user data.
- Support different performance tiers and caching options.
- Charged separately.

---

## Networking Resources

### 5. **Virtual Network (VNet)**
- Defines the communication boundary.
- Contains **Subnets**.

### 6. **Network Interface Card (NIC)**
- Connects the VM to a subnet within a VNet.
- Is a **separate resource**.
- Includes:
  - **IP configurations**
  - Optional: **Network Security Groups**

### 7. **Public IP Address** *(Optional)*
- Binds to a NIC.
- Instance-level IP for external access.
- Charged separately.

### 8. **Network Security Group (NSG)**
- Controls inbound/outbound traffic.
- Can be applied at:
  - **Subnet level** (preferred)
  - **NIC level**

---

## Billing Considerations

You are billed for:
- VM compute usage (size x uptime)
- OS and data disks (based on type & size)
- Public IP (for static or standard SKUs)
- Egress traffic:
  - Between regions
  - Peered VNets
  - Private endpoints

> ⚠️ VNets and NICs are not directly billed, but traffic over them may be.

---

## Resource Group Organization

- Best practice: **Group resources with shared lifecycle**.
  - VM
  - NIC
  - Disks
  - Public IP
  - NSG
- VNet might be shared across VMs and managed separately.

---

## Additional Services (Optional)

- **Extensions** (e.g., Custom Script, Monitoring agents)
- **Log Analytics Workspace** for metrics/logs
- **Azure Bastion** for secure, agentless RDP/SSH access
- **VM Insights**, **Backup**, or **Update Management**

---

## Summary Diagram

```txt
   +-------------------------+
   |     Virtual Machine     |
   +-----------+-------------+
               |
        +------+------+
        |  Network NIC |
        +------+------+
               |
         +-----v------+
         |   Subnet   |
         +-----+------+
               |
         +-----v------+
         |   VNet     |
         +------------+

   Additional Attachments:
   - OS Disk (Managed/Ephemeral)
   - Optional Data Disks
   - Optional Public IP
   - NSG at NIC/Subnet level
