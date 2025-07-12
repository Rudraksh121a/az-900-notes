# Azure Storage Account: Complete Notes (AZ-900)

## Basics of Azure Storage Account

* Azure Storage Account is a fundamental resource used in applications and other Azure services.
* Each storage account has:

  * A **unique name**
  * An associated **resource group**
  * A **specific region** location

> It's best to place storage accounts in the **same region** as compute or database resources to reduce latency and improve performance.

---

## Performance Options

### 1. **Standard Performance**

* Uses **General Purpose v2** accounts
* Supports services: Blob, Queue, Table, File
* Cost-effective and suitable for most workloads

### 2. **Premium Performance**

* Offers **higher performance** at higher cost
* Must select a specific service: Block Blob, Page Blob, or File
* Best for scenarios requiring **low-latency and high-throughput**

> Note: Premium accounts only support **LRS** and **ZRS** redundancy.

---

## Redundancy Options

### Region and Availability Zones

* Azure regions are composed of **Availability Zones** (physically separated data centers)

### Types of Redundancy

| Type    | Description                                                            |
| ------- | ---------------------------------------------------------------------- |
| LRS     | Locally redundant; 3 copies in a single data center                    |
| ZRS     | Zone redundant; 3 copies across Availability Zones                     |
| GRS     | Geo redundant; 3 local + 3 in paired region (asynchronous replication) |
| GZRS    | Combines ZRS in primary + LRS in paired region                         |
| RA-GRS  | GRS + Read access to secondary region                                  |
| RA-GZRS | GZRS + Read access to secondary region                                 |

* **Read Access** (RA) options allow reading from the secondary region.
* Premium supports only **LRS** and **ZRS**.
* Standard supports **all options**.

> Object-level replication allows fine-grained blob replication across regions.

---

## Services in a Storage Account

### 1. **Blob Storage**

* Stores **unstructured data** like images, videos, documents
* Types:

  * **Block Blob**: Most common; stores data in blocks
  * **Page Blob**: Optimized for random access; used by disks
  * **Append Blob**: Ideal for logging scenarios

#### Azure Data Lake Gen2

* Enabled by **Hierarchical Namespace**
* Adds:

  * True folder structure
  * ACLs (Access Control Lists)
  * Analytics APIs

### 2. **File Storage**

* SMB (Windows) or NFS (Linux) based file shares
* Active Directory integration available

#### Azure File Sync

* Syncs **on-prem Windows file servers** with Azure Files
* Offers **cloud tiering** (offloads infrequently used files to Azure)

### 3. **Queue Storage**

* Message queue for decoupled components
* **First In First Out (FIFO)**
* Ideal for event-driven applications

### 4. **Table Storage**

* Schema-less, **NoSQL key-value** store
* Simple, scalable, and inexpensive

### 5. **Static Website Hosting**

* Enabled through a special `$web` container in blob storage
* Supports hosting of HTML, CSS, JS
* Define:

  * Index document
  * Error page

---

## Access Tiers (Blob Storage)

| Tier    | Use Case                        | Storage Cost | Access Cost |
| ------- | ------------------------------- | ------------ | ----------- |
| Hot     | Frequent access                 | High         | Low         |
| Cool    | Infrequent access               | Medium       | Medium      |
| Cold    | Rare access (immediate needed)  | Low          | High        |
| Archive | Long-term storage (rehydration) | Very Low     | Very High   |

* Archive data is **offline** and must be rehydrated to access.
* Minimum retention periods:

  * Archive: 180 days
  * Cold: 90 days
  * Cool: 30 days

---

## Azure Managed Disks

* Use **Page Blob** behind the scenes
* Abstracts the need to manage storage accounts manually

### Disk Types

| Type           | Cost    | Latency | Use Case                      |
| -------------- | ------- | ------- | ----------------------------- |
| Standard HDD   | Low     | High    | Backups, infrequent access    |
| Standard SSD   | Medium  | Medium  | Web servers                   |
| Premium SSD    | High    | Low     | Databases, IO-heavy workloads |
| Premium SSD v2 | Higher  | Lower   | Configurable IOPS/throughput  |
| Ultra Disk     | Highest | Lowest  | Mission-critical workloads    |

* **Bursting** supported by Standard and Premium SSDs
* **Premium SSD v2** and **Ultra Disk** allow **dynamic scaling** of IOPS and throughput

> Disk performance often scales with disk size, but performance tiers allow flexible tuning without resizing.

---

## Lifecycle Management & Storage Tasks

### Lifecycle Management (Free)

* Automates:

  * Moving data between tiers
  * Deleting data
* Based on rules (created/modified/access time)
* Applied per **storage account**

### Storage Tasks (Paid)

* Enterprise-grade automation
* Supports:

  * Tiering
  * Deletion
  * Data protection
  * Immutability
  * Tagging
* Supports wildcards and centralized policies

---

## Summary Table

| Requirement                      | Recommended Service           |
| -------------------------------- | ----------------------------- |
| High-performance workloads       | Premium Storage Account       |
| Cost-optimized long-term data    | Cold / Archive Tier           |
| File share for Windows with sync | Azure File Sync               |
| Persistent storage for VMs       | Azure Managed Disks           |
| Static website hosting           | Blob + Static Website         |
| Event-driven message queue       | Azure Queue Storage           |
| Schema-less NoSQL store          | Azure Table Storage           |
| Regional disaster recovery       | GRS / RA-GRS / GZRS / RA-GZRS |
| Zone failure resiliency          | ZRS / GZRS                    |

---

