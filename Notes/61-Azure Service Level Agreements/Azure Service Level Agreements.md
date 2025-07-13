# Azure Service Level Agreements (SLAs)

## Purpose of SLAs
- SLAs define **Microsoft's commitment** to service **availability and uptime**.
- Useful for customers to understand the **expected reliability** of Azure services.
- SLAs are often expressed in terms of **availability percentages** (e.g., "four nines").

---

## Availability Tiers

| Availability (%) | Downtime/Week       |
|------------------|---------------------|
| 99               | ~1.68 hours         |
| 99.9             | ~10.1 minutes       |
| 99.95            | ~5 minutes          |
| 99.99            | ~1 minute           |
| 99.999           | ~6 seconds          |

---

## SLA Examples for Azure VMs

### 1. **99.99%** SLA
- Requires **2+ VMs** deployed across **2+ Availability Zones** in the **same region**.
- Must use a **Zone-Redundant Load Balancer**.

### 2. **99.95%** SLA
- Requires **2+ VMs** in the same **Availability Set** or **Dedicated Host Group**.

### 3. **Single VM SLA**
- Based on **disk type**:
  - Premium/Ultra SSD: 99.9%
  - Standard SSD: 99.5%
  - Standard HDD: 95%

---

## SLA Documents
- Official SLA documentation includes:
  - **Service-specific SLAs**
  - **Financial backing** (service credits for SLA violations)
  - **Claim process** and **limitations**

---

## SLA Monitoring
- Use **Azure Status Board** to view live service health.
- Use **Service Health Dashboard** for subscription-specific updates.

---

## Composite SLA

### What is it?
- When your solution depends on **multiple services**, the composite SLA is **lower** than any individual SLA.
- Formula for AND dependency:
