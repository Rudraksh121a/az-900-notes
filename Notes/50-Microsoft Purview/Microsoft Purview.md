# Microsoft Purview

Microsoft Purview is a unified data governance solution that helps organizations **understand, manage, protect, and maximize** the value of their data across **clouds, SaaS, and on-premises** environments.

---

## 1. Overview

- **Successor** to Azure Purview and Microsoft 365 Compliance solutions.
- Core Goal: **Understand what data you have, where it is, how it's being used, and how to protect it**.

---

## 2. Supported Data Sources

Microsoft Purview supports scanning and managing data from:

- **Microsoft 365**: SharePoint, Teams, etc.
- **Azure**: Blob, Data Lake, SQL, Cosmos DB, etc.
- **AWS**: S3, RDS, etc.
- **On-premises**: File shares, databases.
- **SaaS platforms**: Power BI, Salesforce, etc.

---

## 3. Free vs Enterprise Version

| Feature                     | Free Version                          | Enterprise Version                     |
|----------------------------|----------------------------------------|----------------------------------------|
| Data catalog               | ✅ Azure-only                          | ✅ All supported sources                |
| Data sharing               | Limited (preview)                      | ✅ Full data sharing capabilities       |
| Classifications, lineage   | ❌                                      | ✅                                      |
| Analytics, policy, insights| ❌                                      | ✅                                      |

---

## 4. Core Capabilities

### a. Data Map

- **In-place scanning** of data (no movement/duplication required).
- Supports 200+ **built-in classifiers** (SSNs, credit cards, etc.).
- Allows **custom classification** using patterns.

---

### b. Sensitivity Labels

- Metadata tags (e.g., **PII**, **Confidential**, **Highly Sensitive**).
- Enables **Data Loss Prevention**, retention policies, and other compliance actions.
- Integration with **Microsoft 365 compliance** tools.

---

### c. Data Lineage

- Visualize **data flow and transformations**.
- Track where data came from and where it moved to.

---

### d. Data Catalog

- **Centralized, normalized view** of data across environments.
- Handles **duplicates, renames, multiple locations**.
- Makes it easier to **search, discover, and understand** data assets.

---

### e. Data Sharing (Preview)

- **Read-only, in-place sharing** of data across orgs.
- Example: Share a blob/ADLS Gen2 dataset with another org **without replicating**.
- Invited user can:
  - View data in their own storage account.
  - Run analytics, but not modify source.
- **Owner retains full control** and can revoke access anytime.

---

### f. Access Policies

- Create **data access policies** centrally via Purview.
- Enables **governed access control** for all scanned resources.
- A **new data plane permission model**—external to native data source permissions.

---

### g. Estate Insights

- Provides **high-level governance metrics**:
  - Compliance status
  - Sensitive data distribution
  - Usage trends
- Useful for **C-level stakeholders** to take decisions and actions.

---

## 5. Analytics & Integration

- Leverage Microsoft Purview insights through:
  - Built-in dashboards
  - Integration with external BI tools

---

## 6. Key Benefits

✅ Classify and label sensitive data  
✅ Avoid data leaks and exposure  
✅ Govern hybrid/multi-cloud data  
✅ Centralize compliance and security  
✅ Improve audit readiness and data hygiene  
✅ Enable safe sharing and collaboration

---

## 7. Summary Table

| Feature                | Description                                      |
|------------------------|--------------------------------------------------|
| Data Map               | Scans & maps data in place                       |
| Classifications        | Detect PII, sensitive data via rules             |
| Sensitivity Labels     | Metadata to enforce actions (e.g., DLP)         |
| Lineage                | Tracks data flow & transformation                |
| Catalog                | Unified view across all sources                  |
| Data Sharing           | Read-only sharing without duplication            |
| Access Policy          | Centralized access control                       |
| Estate Insights        | Organization-wide governance & compliance stats |

---

Microsoft Purview empowers organizations to bring **data visibility, classification, governance, security, and compliance** into one centralized, intelligent system.
