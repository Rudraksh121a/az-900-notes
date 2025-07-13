# Azure Network Security: Network Security Groups (NSGs)

## 🔹 Topics Covered
- What is a Network Security Group (NSG)?
- Default behavior of Azure virtual networks
- Inbound and outbound communication rules
- Components of NSG rules
- Service Tags and Application Security Groups
- Applying NSGs to subnets or NICs
- Best practices and management tips

---

## What is an NSG?

A **Network Security Group (NSG)** is a set of security rules that control **inbound and outbound traffic** to Azure resources within a **virtual network (VNet)**.

- NSGs can be applied to **subnets** or **individual network interfaces (NICs)**.
- They act as a **stateful firewall** for your Azure resources.

---

## Virtual Network Basics

- A **Virtual Network (VNet)** exists in a **single region** and **subscription**.
- VNets are divided into **subnets** that allow **free communication** by default.
- **Peered VNets** or **site-to-site VPN/ExpressRoute connections** are treated as part of the same trusted network.
- Outbound internet access is allowed by default; inbound is **denied**.

---

## Why Use NSGs?

To apply **granular control** over:
- Subnet-to-subnet communication
- Inbound access from the internet
- Communication to/from peered VNets or on-prem networks

---

## NSG Rule Components

Each NSG contains multiple rules defined by:
- **Name**
- **Priority** (lower number = higher priority)
- **Source/Destination**:
  - IP address
  - Subnet
  - Service Tag (e.g., `Internet`, `VirtualNetwork`)
  - Application Security Group (ASG)
- **Port Number** (custom or predefined)
- **Protocol** (`TCP`, `UDP`, `Any`)
- **Action**: `Allow` or `Deny`

---

## Default NSG Rules

NSGs include some **built-in default rules**:
- Allow all traffic **within the VNet**
- Allow traffic from **Azure Load Balancer**
- Deny all other **inbound** traffic
- Allow all **outbound** traffic to the internet
- Deny other outbound traffic not covered above

These defaults have a **high priority number (e.g., 65,500+)**, meaning your custom rules (with lower numbers) can override them.

---

## Service Tags

- Simplify management by grouping **IP ranges** of Azure services.
- Examples:
  - `Internet`: All external IPs
  - `VirtualNetwork`: All IPs in the current VNet and connected peers
  - `AzureLoadBalancer`: Azure's internal LB services
  - Region-specific service tags like `Storage.WestEurope`

---

## Application Security Groups (ASGs)

- Tags applied to **VM NICs** to group them logically.
- Use ASGs as **source/destination** in NSG rules.
- Helps avoid managing individual IP addresses.

---

## Applying NSGs

You can link NSGs to:
- **Subnets** (recommended): applies to all NICs in that subnet
- **Network Interface Cards (NICs)**: more granular, but harder to manage

> Best Practice: **Apply NSGs at the subnet level** unless specific scenarios require NIC-level control.

---

## NSG Rule Example

| Priority | Source         | Destination      | Port  | Protocol | Action |
|----------|----------------|------------------|-------|----------|--------|
| 100      | Internet       | Subnet Frontend  | 443   | TCP      | Allow  |
| 200      | VirtualNetwork | VirtualNetwork   | Any   | Any      | Allow  |
| 65000    | *              | *                | *     | *        | Deny   |

---

## Key Notes

- NSGs are **not hardware firewalls** — rules are enforced **on the virtual switch** of the VM host.
- Even if NSG is linked at both **subnet** and **NIC**, **both sets of rules** apply.
- NSGs work with **stateful** traffic: return traffic is automatically allowed.

---

## When to Use NSGs

Use NSGs to:
- Restrict communication between subnets
- Control access to/from internet or on-premises
- Allow only specific services like HTTPS (port 443)
- Secure backend services from public exposure

---

## Summary

- **NSGs** provide a customizable and stateful way to control traffic in your virtual network.
- Combine NSGs with **Service Tags** and **ASGs** for simplified and scalable management.
- Prefer applying NSGs to **subnets**, not individual NICs, for easier rule control.

