# Identifying the Right Azure Service Type Based on Use Case

## Objective
Understand **which Azure service to choose** based on specific **use case scenarios**. This is commonly tested in Azure certifications.

---

## Service Models Recap

| Type                          | Description                                             | Example                     |
|-------------------------------|---------------------------------------------------------|-----------------------------|
| **On-Premises**               | Everything is managed by you.                          | Traditional data centers    |
| **IaaS (Infrastructure)**     | You manage OS & apps. Azure manages hardware.          | Azure Virtual Machines      |
| **PaaS (Platform)**           | You manage apps/data. Azure manages infra & OS.        | App Service, Azure Functions |
| **SaaS (Software)**           | Fully managed. You use the app directly.               | Microsoft 365               |

---

## Choosing the Right Service Type

### 1. SaaS – Full Business Function Delivered
- **Use When:** You want a complete, ready-to-use solution with no infrastructure to manage.
- **Example:**  
  - Email, collaboration → Use **Microsoft 365**  
  - No need to install/manage Exchange or SharePoint.

---

### 2. IaaS – Full OS Access and Control
- **Use When:**
  - You're lifting and shifting from on-premises.
  - You need full access/control over the OS.
- **Example:**  
  - Moving file servers or domain controllers → Use **Azure Virtual Machines**

---

### 3. PaaS (App Services) – Web Applications
- **Use When:**
  - Hosting web applications (e.g., Apache Tomcat, IIS)
  - Want to reduce infrastructure responsibility.
- **Example:**  
  - Web-based application → Use **Azure App Services**

---

### 4. Azure Container Instances (ACI) – Single Container
- **Use When:**
  - You need to run a single Docker container quickly.
  - No need for orchestration.
- **Example:**  
  - One-off or scheduled Docker task → Use **ACI**

---

### 5. AKS (Azure Kubernetes Service) – Complex Containers
- **Use When:**
  - You have a microservices-based architecture.
  - Require autoscaling, load balancing, orchestration.
- **Example:**  
  - Multi-container app with scalability → Use **AKS**

---

### 6. Azure Functions – Serverless Code Execution
- **Use When:**
  - Trigger code execution based on events (e.g., file upload, queue message).
  - Want a serverless, scalable solution.
- **Example:**  
  - Code runs on file upload to blob → Use **Azure Functions**

---

### 7. Logic Apps – No-Code Workflow Automation
- **Use When:**
  - You need a visual designer for workflows.
  - Minimal or no code should be written.
- **Example:**  
  - Tweet triggers API call → Use **Logic Apps**

---

## Summary Table

| Use Case                             | Recommended Azure Service     |
|-------------------------------------|-------------------------------|
| Email, Messaging, Collaboration     | SaaS → Microsoft 365          |
| Migrate file/domain servers         | IaaS → Azure Virtual Machines |
| Host web apps                       | PaaS → Azure App Services     |
| Run single container                | ACI                           |
| Container orchestration & scaling   | AKS                           |
| Event-driven code (e.g. file added) | Azure Functions               |
| Visual workflow (no-code)           | Logic Apps                    |

---
