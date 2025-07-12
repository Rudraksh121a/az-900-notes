# Azure Cloud Service Models & Shared Responsibility

## Key Topics Covered

- Shared Responsibility Model
- Infrastructure as a Service (IaaS)
- Platform as a Service (PaaS)
- Serverless Computing
- Software as a Service (SaaS)

---

## 1. Shared Responsibility Model

### Overview
Cloud responsibilities are **shared** between the **cloud provider (e.g., Azure)** and the **customer**, depending on the service model.

### Key Concept
Responsibility shifts **based on service type**:
- The more control the customer wants → the more responsibility they retain.
- The more managed the service → the more responsibility shifts to the provider.

---

## 2. Layered Responsibilities

| Layer                     | Responsibility Changes Based on Model |
|---------------------------|----------------------------------------|
| Physical Infrastructure   | Always managed by Azure               |
| Network, Storage, Compute | Managed by Azure in IaaS, PaaS, SaaS  |
| Hypervisor/VM Host        | Azure in IaaS and higher               |
| OS, Middleware            | Customer in IaaS, Azure in PaaS/SaaS  |
| Runtime/Frameworks        | Customer in IaaS, Azure in PaaS/SaaS  |
| Application & Data        | Always Customer's Responsibility       |

---

## 3. On-Premises

- **Customer is responsible for everything**:
  - Physical servers
  - Networking
  - Hypervisors
  - OS, runtime, applications
  - Backup, security, patches

---

## 4. Infrastructure as a Service (IaaS)

### Definition
Cloud provider manages core infrastructure. Customer manages VMs and everything inside.

### Azure Responsibility
- Physical hardware
- Networking
- Hypervisor
- Storage

### Customer Responsibility
- OS (Windows/Linux)
- Runtime, libraries
- Application logic
- Data
- Security, patching, backup

### Pros
- High flexibility
- Full control over environment

### Cons
- High operational responsibility

---

## 5. Platform as a Service (PaaS)

### Definition
Azure manages everything except the app and data. Ideal for developers.

### Azure Responsibility
- VM infrastructure
- OS and middleware
- Runtime (e.g., .NET, Java)

### Customer Responsibility
- Application logic
- Data

### Examples
- App Services
- Azure Kubernetes Service (AKS)
- Azure SQL Database

### Pros
- Less management burden
- Focus on business logic

### Cons
- Limited OS/runtime choices
- No root-level control

---

## 6. Serverless Computing

### Definition
An extension of PaaS where:
- No infrastructure to manage or configure
- Charged **only when code runs**
- Event-driven execution

### Examples
- Azure Functions
- Logic Apps

### Trigger Types
- HTTP requests
- Timers
- Blob uploads
- Queue messages

### Pros
- Cost-efficient (no idle billing)
- Auto-scalable
- No infrastructure ops

### Cons
- Limited execution time
- Stateless design required

---

## 7. Software as a Service (SaaS)

### Definition
End-to-end business functionality delivered via the cloud.

### Examples
- Microsoft 365
- Dynamics 365
- Salesforce

### Provider Responsibility
- Everything (infra, app, data, security, availability)

### Customer Responsibility
- Light admin (e.g., adding users, settings)

### Pros
- No maintenance
- Instant value delivery

### Cons
- No customizations beyond offered features

---

## 8. Summary Comparison Table

| Service Model | Managed by Azure                     | Managed by Customer             | Best For                             |
|---------------|--------------------------------------|----------------------------------|---------------------------------------|
| On-Premises   | Nothing                              | Everything                       | Full control, legacy infrastructure   |
| IaaS          | Hardware, Network, Hypervisor        | OS, App, Data                    | Migration, custom VMs                 |
| PaaS          | Infrastructure, OS, Runtime          | App, Data                        | Web/API apps, databases               |
| Serverless    | All infra; charged per execution     | Function logic, minimal configs | Event-driven apps, workflows          |
| SaaS          | Everything                           | Light admin                      | Email, CRM, productivity              |

---

## 9. Cloud Architecture Approach

- **Use SaaS** if a business-ready solution exists.
- **Use Serverless/PaaS** for new cloud-native development.
- **Use IaaS** for lift-and-shift or legacy apps.
- Minimize operational responsibility to focus on business value.

