# Azure Core Compute Resources

##  Goal
Understand **core Azure compute services**, how they're used, and when to apply each one:
- Virtual Machines (VMs)
- VM Scale Sets
- Container Services
- Azure Kubernetes Service (AKS)
- Azure App Services
- Azure Functions & Logic Apps (Serverless)
- Azure Virtual Desktop

---

## 1. Shared Responsibilities in Cloud

### Cloud Fabric Responsibility (Always on Azure)
- **Compute**
- **Storage**
- **Networking**
- **Hypervisor**

---

## 2. Infrastructure as a Service (IaaS)

### Virtual Machines (VMs)
- Virtualize hardware (CPU, Memory, Storage).
- Complete control over OS and software.

**Ideal For:**
- Lift-and-shift migrations
- Full control needed
- Custom setups like domain controllers, self-managed databases

#### VM Configurations
- **Name**, **Region**, **Resource Group**
- **Images:** Windows, Linux, Custom
- **Size/Skus:**
  - vCPUs, Memory (GiB), Disk, Network performance
  - Examples:
    - General Purpose (1 vCPU: 4 GiB)
    - Compute Optimized (1:2)
    - Memory Optimized (1:8)

#### Management Features
- Auto-shutdown
- Patch management
- Disaster Recovery
- Anti-malware extensions

---

## 3. Virtual Machine Scale Sets (VMSS)
- Automatically deploy/manage **multiple VMs**
- Define:
  - VM Template (OS, size, config)
  - **Scale Rules**: CPU threshold, queue depth

**Ideal For:**
- Load-balanced apps
- Resilient services with auto-scale

---

## 4. Containers (Lightweight Virtualization)

### Concept
- Virtualizes **OS layer** (not hardware)
- Faster than VMs
- Suitable for **microservices**

#### Components:
- **Container Image** (base OS + runtime + app)
- **Container Registry** (stores images)
- **Container Runtime** (creates & runs containers)
- **Container Host** (runs multiple containers)

---

## 5. Azure Container Services

### 🔹 Azure Container Instance (ACI)
- Run single/multiple containers **without managing VMs**
- Serverless: Pay only while running

**Use Cases:**
- Quick tasks
- Event-driven executions
- Minimal orchestration

### 🔹 Azure Kubernetes Service (AKS)
- Fully-managed Kubernetes cluster

**Handles:**
- Networking
- Auto-scaling
- Identity, Policies
- Persistent storage

#### Components:
- **Control Plane** (Managed by Azure)
- **Node Pools** (VM Scale Sets)

**Supports:**
- Helm, YAML, GitOps

---

## 6. Azure App Service

### 🔹 Overview
- Fully managed **PaaS** for:
  - Web apps
  - APIs
  - Mobile backends

**Supports:**
- .NET, Java, Python, PHP, Node.js

### 🔹 App Service Plan
- Define VM size/sku
- Auto-scale & deployment slots
- Can also run **containers**

---

## 7. Serverless Compute (Event-driven Execution)

### 🔹 Azure Functions
- Write code triggered by events (timers, APIs, queues)
- Scales automatically

**Languages Supported:**
- .NET, Node.js, Python, Java, PowerShell

### 🔹 Logic Apps
- Low-code visual designer for **workflow automation**
- Built-in connectors: Twitter, Dropbox, Email, etc.
- Drag-and-drop interface with **templates**

| Feature            | Azure Functions | Logic Apps            |
|--------------------|------------------|------------------------|
| Developer-focused  | ✅                | ❌ (low-code)          |
| Visual Designer    | ❌                | ✅                    |
| Stateless          | ✅                | ❌ (Stateful)          |
| Custom Code        | ✅                | Limited               |
| Event Triggered    | ✅                | ✅                    |

---

## 8. Azure Virtual Desktop (AVD)

### Overview
- Desktop-as-a-Service (DaaS)
- Offers:
  - Full remote desktops
  - Published individual apps

### Components:
- Host pools (VMs in your subscription)
- Connection broker
- Remote desktop gateway

**Use Cases:**
- Secure remote work
- App delivery to mobile/desktop
- Integration with enterprise networks

---

## 9. Summary Decision Table

| Service                   | Best For                                                  |
|---------------------------|-----------------------------------------------------------|
| **Virtual Machine (VM)**  | Full control, legacy workloads                            |
| **VM Scale Sets**         | Auto-scaling multiple VMs                                 |
| **Container Instance**    | Lightweight, quick container jobs                         |
| **Azure Kubernetes (AKS)**| Advanced container orchestration                          |
| **App Service**           | Managed web/mobile apps, APIs                             |
| **Azure Functions**       | Serverless code execution, triggered tasks                |
| **Logic Apps**            | Visual automation, low-code workflows                     |
| **Azure Virtual Desktop** | Virtual desktops or app publishing for remote access      |

---

**Tip:** Pick the compute resource based on workload need:
- Full control ➜ VM
- Scalable microservices ➜ AKS
- Simple workloads ➜ ACI / App Service
- Event-driven tasks ➜ Functions / Logic Apps
- Desktop experience ➜ Azure Virtual Desktop
