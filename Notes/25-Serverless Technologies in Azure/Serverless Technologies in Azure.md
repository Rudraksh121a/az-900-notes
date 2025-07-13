# Serverless Technologies in Azure

## 1. What is Serverless?

Serverless computing allows you to focus on writing code or building workflows without managing infrastructure.

### Key Characteristics:
- **No infrastructure management**
- **Consumption-based billing**: You pay only for the compute used.
- **Event-driven**: Code or workflows are triggered by specific events.

---

## 2. Serverless Triggers

Serverless solutions are initiated by various events:

- A new file written to a **Storage Account**
- A message added to a **Queue**
- A **Scheduled Timer**
- A **REST API call** to an endpoint

---

## 3. Azure Serverless Offerings

Azure offers two main serverless services:

### A. Azure Functions

- Focus on running **custom code**.
- Supports multiple languages:
  - .NET, Node.js, Python, Java, PowerShell, Custom handlers.
- **Stateless by default** (each function run is isolated).
- **Durable Functions** allow for:
  - Long-running workflows
  - Asynchronous operations
  - Human interaction flows
  - Fan-out/fan-in patterns

#### When to Use:
- You want to write and run custom logic in response to an event.
- You need maximum flexibility and control over the code.

---

### B. Azure Logic Apps

- **No-code / low-code** serverless workflows.
- Designed for **citizen developers**.
- Built using a **graphical designer**.
- Supports **thousands of connectors** to integrate with:
  - SQL Server, Outlook, SFTP, SharePoint, Queues, Event Hubs, Salesforce, and more.

#### Key Components:
- **Triggers**: Start the workflow when an event occurs.
- **Actions**: Steps in the workflow using managed connectors.
- **Templates**: Predefined workflows for common use cases.

#### Example Use Case:
1. A blob is added to storage.
2. Generate a **Shared Access Signature (SAS)**.
3. Call an HTTP endpoint with blob location and SAS.
4. Delete the blob.

#### When to Use:
- You don’t want to write code.
- You need to automate workflows across services.
- You are using well-known APIs or services with existing connectors.

---

## 4. Comparison: Azure Functions vs Logic Apps

| Feature                | Azure Functions                     | Azure Logic Apps                      |
|------------------------|--------------------------------------|----------------------------------------|
| Code Requirement       | Yes (write code)                     | No (graphical designer)                |
| Language Support       | .NET, Node.js, Python, Java, etc.    | Not applicable                         |
| Target Users           | Developers                           | Citizen developers / Business users    |
| Integration            | Via code or bindings                 | Via pre-built connectors               |
| Suitable For           | Custom logic                         | Workflow automation                    |
| State Management       | Stateless / Durable Functions        | Built-in through workflows             |

---

## 5. Summary

- **Serverless** in Azure means event-driven execution and consumption-based pricing.
- **Azure Functions** are for custom, stateless (or durable) code logic.
- **Logic Apps** are for orchestrating workflows using a graphical interface.
- Both services are powerful tools to build scalable, efficient, and automated solutions.

