# Azure Sovereign Regions

Azure Sovereign Regions are **physically and logically isolated** Azure environments created to meet specific **governmental or regulatory requirements** that cannot be addressed in the regular **commercial cloud**.

---

## Key Points

- **Multiple Azure Environments Exist:**
  - Azure Public (Commercial)
  - Azure US Government
  - Azure China
  - Azure Germany (legacy)

Use `az cloud list` or `Get-AzEnvironment` to view different environments.

---

## Characteristics of Sovereign Regions

- **Completely Independent Environments**:
  - Separate **datacenters**, **networks**, **hardware**
  - Separate **Azure AD** instances
  - Own **endpoints** and **authentication**
  - Run Azure software, but isolated

---

## Why Use Sovereign Clouds?

Some countries or sectors require:
- Data **residency**, **sovereignty**, and **local access**
- Government personnel to **operate services**
- Specific **security certifications**
- Restrictions on foreign tech operators

---

## Examples

### 1. **Azure US Government**
- Used by: U.S. federal, state, local, tribal governments, and their contractors
- Additional Certifications:
  - CJIS (Criminal Justice)
  - ITAR (Defense)
  - DoD L4/L5
  - FedRAMP High (also in regular Azure)
- Operated **exclusively by screened U.S. personnel**

---

### 2. **Azure China**
- Operated by **21Vianet** (not Microsoft)
- Meets Chinese regulatory laws
- Uses licensed Azure technology
- Separate endpoints and isolated services

---

### 3. **Azure Germany**
- **Legacy** sovereign cloud, not used for **new customers**
- Now replaced with **commercial Azure regions** in Germany that meet **EU data protection** and **sovereignty laws**

---

## Summary Table

| Region            | Operated By     | Key Use Case                               | Isolated? |
|-------------------|------------------|--------------------------------------------|-----------|
| Azure Public      | Microsoft         | General use worldwide                      | No        |
| Azure Government  | Microsoft (US)    | U.S. Gov Agencies & Contractors            | Yes       |
| Azure China       | 21Vianet (China)  | Mainland China, legal sovereignty          | Yes       |
| Azure Germany     | Microsoft         | Legacy, replaced by modern commercial regs | Yes*      |

---

## Exam Tip

Understand:
- Sovereign regions are used for **compliance**, **data sovereignty**, and **restricted operations**
- Each sovereign cloud is **fully separated** from regular Azure
- Not all services or regions are available in these clouds

