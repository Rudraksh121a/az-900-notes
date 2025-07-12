# Azure Arc

Azure Arc extends Azure’s control plane and governance capabilities to infrastructure and services outside of Azure, such as on-premises environments or other cloud platforms like AWS and GCP.

---

## Purpose

Azure provides:
- Massive global capacity via regions
- Resources like VMs, AKS, App Services, Machine Learning, etc.
- Governance tools:
  - **Azure Policy**
  - **Role-Based Access Control (RBAC)**
  - **Tagging**
  - **Microsoft Defender for various services**

However, many organizations also run workloads **outside Azure**, such as:
- On-premises data centers
- Other cloud providers (e.g., AWS, GCP)

**Azure Arc brings Azure governance and management capabilities to those environments.**

---

## How Azure Arc Works

Azure Arc extends the **Azure Resource Manager (ARM)** control plane to non-Azure resources. You can now apply governance, security, automation, and visibility just like you would for native Azure resources.

---

## Arc-Enabled Servers

- Supports: **Windows, Linux, Virtual Machines, Bare-metal Servers**
- Works by installing an **Arc Agent** on the machine
- Enables:
  - Azure Policy
  - RBAC
  - Defender for Cloud
  - Tagging
  - Patch management
  - Azure Resource Graph and Inventory
  - Managed Identity for secure service interaction

---

## Arc-Enabled Kubernetes

- Supports: Any **CNCF-compliant** Kubernetes clusters (on-premises, AWS, GCP, etc.)
- Arc extends:
  - Azure Policy
  - Defender for Kubernetes
  - GitOps support (auto-deploy manifests from a Git repo)
  - Tagging
  - Monitoring

---

## Arc-Enabled Services

Once Kubernetes is Arc-enabled, Azure can run additional services **on top of those clusters**, including:

### 1. Data Services
- SQL Managed Instance
- PostgreSQL Hyperscale

### 2. Application Services
- App Services
- Functions
- Logic Apps

### 3. Machine Learning
- Model training and inferencing at edge or other environments

### 4. VMware Support
- Lifecycle management for VMs: create, start, stop, resize, delete via Azure

---

## Azure Arc Use Cases

- **Unified governance** across hybrid/multi-cloud
- **Security and compliance** extension via Defender & Policy
- **Automation and patching** in on-prem/cloud servers
- **Centralized DevOps** using GitOps for Kubernetes
- **Hybrid cloud enablement** via Azure services on other infrastructure

---

## Summary

Azure Arc enables a **consistent, centralized management experience** for resources:
- **Anywhere** they run—on-prem, edge, or in other clouds
- **Through the Azure control plane**, using tools like:
  - Azure Resource Manager
  - Azure Policy
  - Defender for Cloud
  - Tagging, RBAC, GitOps, and more

Arc empowers true **hybrid cloud** capabilities with Azure's governance, security, and services extended across your entire infrastructure.

