# Azure Core Networking Resources 

## Objective
Understand the **benefits and usage** of the following networking components in Azure:

- Virtual Networks (VNets)
- Subnets
- VNet Peering
- VPN Gateway
- ExpressRoute
- Public IPs, Service Endpoints, Private Endpoints

---

## 1. Azure Virtual Network (VNet)

- A **VNet** is a core building block for networking in Azure.
- It exists within a **single subscription** and a **specific region**.
- Cannot span regions or subscriptions.

### Addressing
- Requires at least **one IPv4 address space** (CIDR block).
- Usually uses **RFC1918 private IP ranges**:
  - 10.0.0.0/8
  - 172.16.0.0/12
  - 192.168.0.0/16
- Optionally supports **IPv6** address spaces.

---

## 2. Subnets

- A VNet is divided into **subnets**, which are smaller address spaces from the main CIDR.
- Subnets **span availability zones** within a region.
- Subnetting examples:
  - 10.0.1.0/24
  - 10.0.2.0/24
- Resources are assigned to a subnet through a **Network Interface Card (NIC)**.

### Subnet Sizing
- Every subnet loses **5 IP addresses**:
  - 1 for network address
  - 1 for broadcast address
  - 1 for gateway
  - 2 for DNS

---

## 3. Public IP Address

- A **Public IP** is a separate resource.
- It can be attached to:
  - A VM’s NIC
  - A **Load Balancer’s front end**
- Enables inbound internet access.

### Outbound Internet Access
- Azure allows outbound internet by default using:
  - Load balancer’s public IP
  - NAT gateway (if configured)

---

## 4. VNet Peering

- Connects two VNets using Azure's **private backbone**.
- Can be:
  - **Regional peering** (same region)
  - **Global peering** (different regions)
- Can span:
  - Regions
  - Subscriptions
  - Azure AD tenants (if trust exists)
- IP address ranges **must not overlap**.

---

## 5. On-Premises Connectivity

### 5.1 VPN Gateway

- Enables encrypted communication **over the internet** between on-premises and Azure.
- Requires:
  - VPN gateway in Azure
  - VPN device on-premises

#### Two Types:
1. **Policy-based** (legacy, static routes, limited)
2. **Route-based** (preferred, supports multiple connections and point-to-site)

### 5.2 VPN Gateway Modes

- **Active-passive**: One public IP, failover only on failure
- **Active-active**: Two public IPs, both tunnels active

### 5.3 Point-to-Site VPN

- Connects a single client machine to Azure VNet (e.g., developer working remotely).

---

## 6. ExpressRoute

- Private, dedicated connectivity to Azure via Microsoft backbone.
- Does **not use the public internet**.
- Connectivity models:
  - Layer 2 (Ethernet, P2P)
  - Layer 3 (MPLS, IP VPN)
  - Co-location provider

### 6.1 Peering Types

1. **Private Peering**
   - Connects to Azure VNets via **ExpressRoute Gateway**.
   - Uses **BGP** for routing.
   - Can access peered VNets (via remote gateway setting).

2. **Microsoft Peering**
   - Access public Microsoft services (e.g., Azure SQL, Storage) without going over the internet.
   - Requires a **route filter** to select allowed services.

---

## 7. Service Endpoints

- Enables VNet to **access Azure services** over the Microsoft backbone instead of the public internet.
- Improves routing and security.
- Allows subnets to be **whitelisted** on service firewalls (e.g., Storage Account).

---

## 8. Private Endpoints

- Provides **private IP access** to PaaS services.
- Assigns a private IP from the VNet subnet to the service.
- Entirely disables public access if desired.
- Useful for services like:
  - Azure Storage
  - Azure SQL
  - Cosmos DB

---

## Summary

| Concept             | Purpose                                                   |
|---------------------|-----------------------------------------------------------|
| Virtual Network     | Isolates network resources in a region and subscription   |
| Subnet              | Logical division of VNets; defines IP address allocation  |
| Public IP           | Enables external internet access                          |
| VNet Peering        | Connects two VNets via Azure backbone                     |
| VPN Gateway         | Encrypted tunnel over internet to on-premises             |
| ExpressRoute        | Dedicated, private Azure connection                       |
| Service Endpoint    | Secure VNet-to-service communication over Azure backbone  |
| Private Endpoint    | Assigns private IP to service for secure VNet access      |

---

## Best Practices

- Always use **non-overlapping IP ranges** for VNets and subnets.
- Prefer **route-based VPNs** over policy-based.
- Use **VNet peering** for Azure-to-Azure connectivity.
- Use **ExpressRoute** for consistent, private, high-performance connection.
- Use **private endpoints** to restrict PaaS access to VNets only.
- Use **service endpoints** when private endpoint is not needed but secure routing is.

