# Azure Network Security: Azure DDoS Protection

## 🔹 Topics Covered
- What is a DDoS attack?
- Types of DDoS attacks (volumetric, protocol, application)
- Azure's default (basic) DDoS protection
- Standard DDoS Protection Plan
- Adaptive tuning and alerts
- Rapid response and SLA credits
- Multi-subscription and multi-VNet coverage

---

## What is a DDoS Attack?

**Distributed Denial of Service (DDoS)** attacks aim to **disrupt the availability** of a service or application by overwhelming it with traffic or exploiting weaknesses.

### Types of DDoS Attacks
1. **Volumetric Attacks**
   - Flood bandwidth with ICMP/UDP packets
   - Example: ICMP Flood, UDP Flood

2. **Protocol Attacks**
   - Exploit weaknesses in TCP/UDP stack
   - Example: SYN Flood, Ping of Death, malformed packets

3. **Application Layer Attacks**
   - Target the application itself
   - Example: HTTP flooding, Slowloris (slow post/read)

---

## Azure Basic DDoS Protection

 **Enabled by default** on all Azure public-facing resources  
 No customization, metrics, or alerts  
 Primarily protects **Azure platform**, not individual apps

---

## Azure DDoS Standard Protection

To protect your specific apps and resources, use the **DDoS Standard Protection Plan**.

###  How It Works:
- You **create a DDoS Standard Plan**
- Link it to one or more **Virtual Networks (VNets)**
- All **Public IPs** within those VNets are protected
- Covers up to **100 Public IPs**, more with additional cost

###  Key Features:
| Feature                         | Basic      | Standard     |
|-------------------------------|------------|--------------|
| Auto attack detection         | ✅          | ✅            |
| Adaptive tuning               | ❌          | ✅ (ML-based) |
| Metric visibility             | ❌          | ✅            |
| Azure Monitor integration     | ❌          | ✅ Alerts     |
| Application-aware tuning      | ❌          | ✅            |
| Rapid Response Team (support) | ❌          | ✅            |
| SLA credits                   | ❌          | ✅            |
| Multi-subscription support    | ❌          | ✅            |
| Flow logs and reporting       | ❌          | ✅            |

---

## Adaptive Tuning

- Uses **Machine Learning** to learn normal traffic patterns
- Adapts thresholds based on actual usage
- Reduces false positives

---

## Monitoring & Alerts

- Provides **metrics** for traffic and attack patterns
- Integrates with **Azure Monitor**, **Alerts**, and **Action Groups**
- Enables automated actions on detection

---

## Rapid Response & SLA Protection

- Access to **Microsoft support team** during active attacks
- If auto-scaling kicks in due to an attack, you can claim **cost credits**
- Helps with **forensic analysis** post-attack

---

## Multi-VNet, Multi-Subscription Usage

- A **single DDoS Protection Plan** can be:
  - Shared across **multiple VNets**
  - Used in **multiple Azure subscriptions**
- Provides **centralized billing** and easier management

---

##  Summary

- **Basic DDoS Protection** is free, automatic, and designed to protect Azure’s infrastructure.
- **Standard DDoS Protection** is paid, app-aware, and designed to protect *your* application.
- Standard is best for:
  - Mission-critical apps
  - Public-facing services
  - Scenarios needing visibility, alerts, and quick response

---

