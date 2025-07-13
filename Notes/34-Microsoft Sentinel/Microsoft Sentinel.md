# Microsoft Sentinel (formerly Azure Sentinel)

## Lesson Overview
Microsoft Sentinel is a **cloud-native SIEM (Security Information and Event Management)** and **SOAR (Security Orchestration, Automation, and Response)** solution built on Azure.

---

## Key Features

### 1. SIEM (Security Information and Event Management)
- Collects and analyzes **security data** from multiple sources.
- Helps detect and investigate **security incidents**.
- Centralizes visibility of security-related logs.

### 2. SOAR (Security Orchestration, Automation and Response)
- Automates responses to security threats.
- Uses **Playbooks** and **Logic Apps** to trigger actions (e.g., disable accounts, block IPs).

---

## Sentinel Architecture

### Built on:
- **Log Analytics Workspace** from Azure Monitor.

### Data Sources:
- Azure resources
- On-premises infrastructure
- Other cloud environments (AWS, GCP)
- Network devices
- SaaS applications (e.g., Microsoft 365, Google Workspace)
- Identity platforms (e.g., Azure AD)

---

## Data Connectors

- **Purpose**: Bring in data from various services and tools.
- **Examples**:
  - Azure AD, AWS, F5, Cisco, Barracuda, Apache, Microsoft 365 Defender
- Each connector brings:
  - Logs
  - Queries
  - Workbooks

> More connectors = better data insight and threat correlation.

---

## Core Capabilities

### 1. **Log Collection and Analysis**
- Uses **Log Analytics** to gather large volumes of security logs.
- Supports **Kusto Query Language (KQL)** for custom analysis.

### 2. **Incident Detection**
- Uses **machine learning** and threat intelligence.
- Detects anomalies and suspicious activities.
- Presents in dashboards (overview, maps, etc.).

### 3. **Hunting**
- Manual or assisted searching for potential threats.
- Based on predefined queries like:
  - Rare audit activity
  - Abnormal sign-in behavior

### 4. **Workbooks**
- Visual tools for reporting and investigation.
- Prebuilt templates for specific threat types.

### 5. **Notebooks**
- Based on Jupyter Notebooks.
- For advanced investigation and custom analysis.

### 6. **Entity Behavior**
- Builds behavioral profiles of users, devices, and apps.
- Flags deviations from normal behavior.

### 7. **Threat Intelligence**
- Ingests threat feeds: IPs, domains, file hashes.
- Detects known malicious entities in the environment.

---

## Automation Capabilities

- **Automation Rules**: Predefined rules that act on certain triggers.
- **Playbooks**:
  - Built on **Azure Logic Apps**
  - Example actions:
    - Block IP addresses
    - Disable compromised user accounts
    - Alert IT via email/SMS

---

## Summary Table

| Feature             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| SIEM                | Detects and investigates security incidents                                 |
| SOAR                | Automates response to detected threats                                      |
| Data Connectors     | Ingest logs and data from various sources                                   |
| Log Analytics       | Core storage and query engine                                               |
| Incidents           | Alert groupings to investigate and track                                    |
| Hunting             | Manual or proactive search for known patterns or vulnerabilities            |
| Playbooks           | Automated response logic via Logic Apps                                     |
| Workbooks           | Dashboards for data visualization                                           |
| Notebooks           | Jupyter-based investigation environment                                     |
| Entity Behavior     | User and device behavior analytics                                          |
| Threat Intelligence | Uses internal and external threat data for better detection                 |

---

## Real-World Example Use Cases

- Detect brute-force attacks against user accounts.
- Alert on unusual geographic login patterns.
- Block malicious IPs automatically via playbooks.
- Monitor audit logs from Microsoft 365 and AWS.

---

## Tips for AZ-900

- **Sentinel = SIEM + SOAR**
- Sits on top of **Log Analytics Workspace**
- Uses **KQL** for querying logs
- Collects data via **connectors**
- Enables **incident response automation** via playbooks
- Leverages **AI and ML** to enhance threat detection

---


