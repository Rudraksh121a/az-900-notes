# Types of Cloud Computing

## Objective
Understand the **differences between cloud computing types** and **key concepts** assessed in AZ-900:
- Define cloud computing
- Describe Public, Private, and Hybrid cloud
- Compare and contrast all three

---

## Core Principles of Cloud Computing

### 1. **Resource Pooling**
- Avoids isolated resources (islands)
- Combines all infrastructure into a **shared resource pool**
- Enables **efficiency and elasticity** across business units

### 2. **Self-Service**
- Users can provision resources **on-demand** without admin intervention
- Controlled via:
  - **Quotas**
  - **Policies**
  - **Templates**
- Supports:
  - **Showback**: See what is used
  - **Chargeback**: Bill for what is used

---

## Types of Cloud

### 1. **Public Cloud**

- **Definition**: Services offered by third-party providers over the internet
- **Example**: Azure
- **Features**:
  - Fully managed by provider
  - True **OpEx** model – pay only for what you use
  - Scalable across **many regions**
  - Massive service variety: VMs, databases, AI, storage, etc.
  - Accessed over internet or private network (e.g. ExpressRoute)
  - Offers:
    - Role-based access control (RBAC)
    - Governance policies
    - Self-service capabilities
    - Software-defined infrastructure

---

### 2. **Private Cloud**

- **Definition**: Cloud infrastructure used exclusively by a single organization
- **Hosted**: On-premises or in a dedicated environment
- **Features**:
  - Controlled by the company
  - Requires **management stack** (e.g., hypervisor + management software)
  - Enables internal self-service, quotas, and showback
  - **CapEx** model – upfront purchase of servers, licenses
  - Flexible within the limits of internal resources
- **Examples**:
  - Hyper-V + System Center
  - VMware vSphere + vRealize

---

### 3. **Hybrid Cloud**

- **Definition**: Combines **public** and **private** cloud environments
- **Use Cases**:
  - Burst to public cloud in peak usage
  - Failover scenarios
  - Keep sensitive workloads on-premises
  - Operate in regions without public cloud data centers
- **Goal**:
  - **Consistent management & developer experience**
  - Use same tools, policies, and governance across environments

#### Azure Hybrid Solutions
- **Azure Arc**:
  - Extend Azure management (RBAC, policies, monitoring) to on-prem/cloud
- **Azure Stack**:
  - Run Azure services in private cloud
  - Variants:
    - **Azure Stack Hub**: Full Azure services in your datacenter
    - **Azure Stack Edge**: Compact appliance for edge computing
    - **Azure Stack HCI**: Hyper-converged infrastructure with Azure integration

---

## Summary Table

| Feature                    | Public Cloud               | Private Cloud              | Hybrid Cloud                            |
|----------------------------|----------------------------|----------------------------|------------------------------------------|
| Ownership                  | Cloud provider             | Single organization        | Both                                     |
| Deployment Location        | Off-site (Azure, etc.)     | On-premises or hosted      | Mix of on-prem & cloud                   |
| Cost Model                 | OpEx (pay-as-you-go)       | CapEx (upfront investment) | Mixed                                    |
| Accessibility              | Over the internet          | Internal network           | Both                                     |
| Scalability                | Virtually unlimited        | Limited by hardware        | Depends on implementation                |
| Management Responsibility  | Provider                   | Organization               | Shared                                   |
| Examples                   | Microsoft Azure            | VMware, Hyper-V clusters   | Azure + Azure Stack / Arc combo          |

---

## Key Takeaways

- **Public cloud** (e.g. Azure) is the most feature-rich and flexible.
- **Private cloud** gives full control, suited for sensitive or legacy workloads.
- **Hybrid cloud** offers a balance, allowing seamless integration of both.

