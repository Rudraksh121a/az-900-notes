# Azure Core Services: Availability Zones

## 1. What Are Availability Zones?

Availability Zones (AZs) are **physically separate data centers** within a region, each with:
- Independent **power**
- Independent **cooling**
- Independent **networking**

These provide **resiliency at the data center (facility) level**.

---

## 2. Availability Zones Within a Region

- Each **supported Azure region** has **3 availability zones** (AZ1, AZ2, AZ3).
- These zones are **logical mappings** and can vary between subscriptions.

### Example:
- In Subscription A, AZ1 = Building A, AZ2 = Building B  
- In Subscription B, AZ1 may = Building B, AZ2 = Building C  
There is **no fixed physical mapping** across subscriptions.

---

## 3. Why Use Availability Zones?

### a. **Resiliency from Data Center Failure**
- Deploy resources across multiple AZs for **high availability**.

### b. **Disaster Protection**
- If one AZ has a fire, power outage, or networking failure, the others are unaffected.

### c. **Update Protection**
- Microsoft rolls out updates **one AZ at a time** to avoid service-wide issues.

---

## 4. When and How to Use AZs?

### a. **Zonal Services**
- You **choose** the specific AZ.
- Example: When creating a **Virtual Machine (VM)**, you can select AZ1, AZ2, or AZ3.

```bash
Use case:
Deploy VM1 in AZ1, VM2 in AZ2, and VM3 in AZ3
