# Azure Network Security: Azure Firewall

## 🔹 Topics Covered
- Difference between NSG and Azure Firewall
- What Azure Firewall is and where it's used
- Deployment and architecture
- Application and network rules
- TLS inspection with the Premium SKU
- DNAT (Destination Network Address Translation)
- Integration with NSGs and best practices

---

## What is Azure Firewall?

**Azure Firewall** is a **fully managed, cloud-native network security service** that protects Azure Virtual Networks. Unlike **Network Security Groups (NSGs)**, which operate at **Layer 4 (TCP/UDP)**, Azure Firewall can inspect traffic at **Layer 7 (Application Layer)**.

- **Understands URLs, FQDNs, and application-level protocols**
- Can block or allow traffic based on **web categories** (e.g., news, gambling)
- Ideal for **perimeter security** in a **defense-in-depth** model

---

## NSG vs Azure Firewall

| Feature                    | NSG                         | Azure Firewall                 |
|---------------------------|-----------------------------|--------------------------------|
| Layer                     | 4 (TCP/UDP)                 | 4 and 7 (Application)          |
| Application rules         | ❌                          | ✅                             |
| Web category filtering    | ❌                          | ✅ (Premium SKU)               |
| TLS inspection            | ❌                          | ✅ (Premium SKU)               |
| Fully qualified domain    | ❌                          | ✅                             |
| Stateful                  | ✅                          | ✅                             |
| NAT support               | ❌                          | ✅ (DNAT/SNAT)                 |
| Use case                 | Subnet-level control         | Edge-level centralized control |

---

## Architecture and Deployment

- Azure Firewall is deployed in a **dedicated subnet** named `AzureFirewallSubnet`
- It uses **VM scale sets** behind the scenes
- Automatically **scales** based on traffic
- You configure **User Defined Routes (UDRs)** to **route traffic** from other subnets to the firewall

---

## Types of Rules in Azure Firewall

### 1. **Application Rules** (Layer 7)
- Filter traffic based on:
  - **FQDNs (Fully Qualified Domain Names)**
  - **URLs**
  - **Web categories** (e.g., social media, malware)
- Example: Allow only access to `microsoft.com`, block `facebook.com`

### 2. **Network Rules** (Layer 4)
- Similar to NSG: filter by **IP address**, **port**, and **protocol**
- Useful for non-HTTP/S traffic like RDP, SSH

---

## Premium SKU Features

- **TLS Inspection**: Decrypts and inspects **encrypted (HTTPS)** traffic
- Works by replacing certificates to inspect the payload
- Enables inspection even when **full URLs are encrypted**

---

## DNAT (Destination NAT)

- Redirect incoming traffic to a specific **internal VM**
- Common for allowing **RDP**, **SSH**, or specific ports from the internet
- Example: Public IP on port 22 → Internal VM on port 22

---

## Integration with NSGs

Azure Firewall works **with NSGs**, not instead of them.

- Use NSGs for **internal subnet-level control**
- Use Azure Firewall for **centralized perimeter control**
- This supports a **defense-in-depth** strategy

---

## Key Advantages

- **Fully managed**: No need to handle VM provisioning or updates
- **Auto-scaling** based on traffic
- Supports **custom DNS** and **FQDN filtering**
- Combine with **Azure Monitor** for logging and alerts

---

## Summary

- Azure Firewall provides **deep traffic inspection**, filtering, and logging capabilities
- Use **User Defined Routes (UDRs)** to direct traffic through the firewall
- Combine **NSGs + Azure Firew**
