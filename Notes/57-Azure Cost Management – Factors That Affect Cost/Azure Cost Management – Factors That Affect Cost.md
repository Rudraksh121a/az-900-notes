# Azure Cost Management – Factors That Affect Cost

Azure uses a **consumption-based pricing model**, meaning you pay for what you use. However, the **actual cost** depends on several variables.

---

## Key Cost-Affecting Factors

### 1. **Resource Type**
- Each resource has its own pricing model (e.g., VM, storage, databases, bandwidth).

---

### 2. **SKU (Stock Keeping Unit)**
- Many resources offer **tiers or versions** (e.g., Basic, Standard, Premium).
- Example: VMs come in D-series, E-series, B-series, etc.

---

### 3. **Tier / Performance Level**
- **Storage** offers performance and access tiers:
  - Performance: Premium vs. Standard
  - Access: Hot, Cool, Archive
- Pricing varies based on these selections.

---

### 4. **Region (Location)**
- Costs **vary by Azure region** due to:
  - Infrastructure costs
  - Network egress pricing
  - Data center operations

---

### 5. **Metering Type**
- Azure meters usage differently:
  - **Provisioned resources** (e.g., IP address): Cost incurred when created
  - **Running resources** (e.g., VMs): Cost only when running
  - **Storage**:
    - Standard: Billed for used space
    - Premium: Billed for provisioned space

---

### 6. **Number of Instances**
- Auto-scaling services increase/decrease based on load
- More instances = higher cost

---

### 7. **Work Performed**
- **Serverless** services (Azure Functions, Logic Apps):
  - Event-driven
  - Charged based on number of executions and execution time

---

### 8. **Amount of Storage**
- Charged based on either:
  - **Used capacity** (e.g., Standard Storage)
  - **Provisioned capacity** (e.g., Premium Files)

---

### 9. **Transactions and Interactions**
- APIs, read/write operations, data transfers can incur additional costs.

---

### 10. **Licensing**
- Includes:
  - Windows, SQL Server
  - Third-party products from Azure Marketplace

---

## 🧠 Cost Optimization Tip

To avoid surprise bills:
- Understand **what you’re provisioning**
- Know **how it is billed** (used vs. provisioned)
- Analyze using:
  - **Azure Pricing Calculator**
  - **TCO (Total Cost of Ownership) Calculator**
  - **Azure Cost Management + Billing**

---

## 📋 Cost Influencers Checklist

| Factor          | Description                                  |
|-----------------|----------------------------------------------|
| Resource Type   | VM, Storage, Network, DB, etc.               |
| SKU             | Different versions or models of resources    |
| Tier            | Performance level or access tier             |
| Region          | Physical location of Azure resources         |
| Meter Type      | Running vs Provisioned, Used vs Reserved     |
| Instance Count  | How many instances are running (auto-scale)  |
| Work Done       | Serverless – based on executions             |
| Storage Volume  | Data stored or provisioned                   |
| Transactions    | Read/write operations, API calls             |
| Licensing       | OS, DB, third-party software                 |

---

Always validate your architecture and usage patterns to keep your **Azure costs optimized**.
