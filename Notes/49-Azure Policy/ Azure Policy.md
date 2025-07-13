# Azure Policy

Azure Policy is a governance tool that enables you to **create, assign, and manage policy definitions** to enforce rules and effects on your Azure resources.

---

## 1. Why Azure Policy?

- In traditional IT, requests for resources were manually reviewed by operations teams.
- In Azure, **self-service provisioning** (via portal, pipelines, DevOps) replaces that.
- Organizations still need to **enforce compliance, security, and governance** without manual approvals.
- Azure Policy helps **enforce requirements** at the **control plane** level (via Azure Resource Manager).

---

## 2. Azure Resource Hierarchy (Where Policy Applies)

Policies can be assigned at different scopes:

- **Management Group**
- **Subscription**
- **Resource Group**
- **Individual Resources**

✅ **Inheritance:** Policies assigned at higher levels are **inherited** by lower levels.

---

## 3. What is an Azure Policy?

- A **Policy** is a rule that defines:
  - **Condition** (What to look for)
  - **Effect** (What to do if the condition is met)

---

## 4. Policy Effects

Azure Policies can have multiple effects:

- `Audit`: Log non-compliant resources without blocking.
- `Deny`: Prevent non-compliant resources from being created.
- `Append`: Add values (like tags) to a resource if not present.
- `Modify`: Change or enforce settings on resources.
- `DeployIfNotExists`: Automatically deploy configurations if missing.
- `AuditIfNotExists`: Log if associated resources/settings are missing.

---

## 5. Initiatives

- A **Policy Initiative** is a **collection of policies** grouped together.
- Useful for:
  - Managing large sets of policies under one assignment.
  - Tracking **overall compliance**.
- Example:
  - `Azure Security Benchmark` is a built-in initiative with 200+ policies.

---

## 6. How Azure Policy Works

- All actions go through **Azure Resource Manager (ARM)**.
- Azure Policy intercepts those actions to **enforce rules**.
- Examples of policy rules:
  - Only allow VMs in `East US`.
  - Require specific SKUs for storage accounts.
  - Enforce resource tags like `CostCenter`, `Owner`, or `Environment`.

---

## 7. Built-in Policy Examples

Azure provides many built-in policies, such as:

- Allow only specific **storage SKUs**
- Deny creation of resources with **public IPs**
- Enforce encryption or tag requirements
- Restrict allowed **regions**, **VM sizes**, etc.

---

## 8. Compliance Tracking

- Azure Policy provides **compliance reports** for each policy/initiative.
- Helps track which resources are **compliant vs. non-compliant**.
- Useful for security audits and regulatory checks.

---

## 9. Best Practices

- **Start with Audit Mode** to assess impact.
- Use **Initiatives** to group related policies.
- Apply general policies at higher levels (Management Group), and specific ones at lower levels (Resource Groups).
- Use **parameters** in policies to make them reusable.
- Integrate with **Azure Security Center / Defender for Cloud** to use policy-based compliance.

---

## 10. Summary

| Concept          | Description                                         |
|------------------|-----------------------------------------------------|
| Azure Policy     | Rule-based governance to enforce org requirements   |
| Scope            | Management Group → Subscription → Resource Group    |
| Inheritance      | Applies downward in the resource hierarchy          |
| Effects          | Audit, Deny, Append, Modify, DeployIfNotExists      |
| Initiatives      | Group of related policies for easier management     |
| Use Cases        | Compliance, tagging, region restrictions, SKU limits|

---

Azure Policy ensures **automatic, consistent governance** across all Azure environments—without human intervention.
