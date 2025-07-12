# AZ-900: Reliability and Predictability in Azure

---

##  Objective

Understand the **difference and relationship between reliability and predictability** in Azure cloud services.  
Learn how Azure ensures service uptime, consistency, and recoverability.

---

## 1. Reliability

### 🔹 Key Idea
Azure services are designed to **handle failures and maintain availability** through **built-in redundancy, auto-healing, and scaling**.

---

### A. **Failures Still Happen**
- Physical infrastructure (servers, disks, racks) can fail.
- Azure handles this automatically via **auto-healing mechanisms**.

### B. **Auto-Healing Examples**
- **VMs**: Automatically redeployed to healthy nodes/racks.
- **Storage**: At least 3 replicas (intra-rack, zone-redundant, or geo-redundant).
- **Databases**: Replicate logs and data to standby instances.

---

### C. **Scaling Reliability**
- **Auto-scaling** increases/decreases service instances based on demand.
- Ensures performance during peak times and reduces cost during idle periods.

---

### D. **SLAs (Service Level Agreements)**
- Azure provides **financially backed SLAs** for each service.
- Composite SLAs apply when multiple services are used together.

---

### E. **Design for Failure**
- Expect regional failures. Use:
  - **Active-Active** deployments across regions
  - **Active-Passive** failover
  - Backups and replicas
- Design decisions depend on:
  - **RPO (Recovery Point Objective)**: How much data loss is acceptable.
  - **RTO (Recovery Time Objective)**: How quickly the service must recover.

---

### F. **Monitoring and Alerts**
- Use:
  - **Azure Monitor**
  - **Application Insights**
  - **Alerts and Action Groups**
- Detect and respond to issues proactively.

---

## 2. Predictability

### 🔹 Key Idea
Azure provides **consistent performance, behavior, and pricing**, enabling organizations to plan and automate deployments and operations.

---

### A. **Defined SKUs and Performance**
- VM SKUs have:
  - Defined CPU performance (ACUs)
  - Memory, IOPS, throughput, network limits
- Storage accounts define:
  - IOPS
  - Throughput
  - Latency

---

### B. **Consistent Behavior**
- Azure APIs and tools behave consistently.
- Supported by:
  - **ARM Templates / Bicep**
  - **Terraform**
  - **CLI / PowerShell**

---

### C. **Pricing Predictability**
- Service prices are predictable and based on region and SKU.

---

### D. **Predictable Deployments**
- Use **declarative templates** (JSON, Bicep, Terraform) to avoid manual errors.
- Ensures same result every time you deploy.

---

### E. **Automation & DevOps**
- Automate tasks with:
  - PowerShell / Azure CLI scripts
  - Azure Automation
  - Event-based actions
- Use **CI/CD Pipelines** with tools like:
  - GitHub Actions
  - Azure DevOps
  - GitLab CI

---

### F. **Human-Free Consistency**
- Avoid manual changes.
- Let automation enforce predictability.

---

## Summary Table

| Concept           | Reliability                                      | Predictability                                      |
|-------------------|--------------------------------------------------|-----------------------------------------------------|
| Definition        | System’s ability to recover from failure         | Consistent and expected behavior                    |
| Techniques        | Auto-healing, redundancy, scaling, SLAs          | Templates, automation, DevOps, consistent SKUs      |
| Tools             | Azure Monitor, Alerts, Geo-redundancy            | ARM, Bicep, Terraform, Azure CLI, Azure DevOps      |
| Goal              | Maximize uptime and recover from issues          | Ensure consistent deployments and operations        |

---

## Best Practices

- **Design for failure**: Use redundancy and backups.
- **Automate everything**: From deployments to scaling.
- **Use templates**: For predictable, repeatable infrastructure.
- **Monitor proactively**: Detect and fix before users notice.
- **Understand SLAs**: Know what Azure guarantees and plan accordingly.

