# Azure Data Movement and Migration Options

## Introduction

Many organizations already have existing **on-premises data**. Depending on how that data is stored, accessed, and planned for cloud usage, Azure offers various **data movement and migration** services.

---

## Azure File Sync

A common scenario is syncing **on-premises SMB file shares** (hosted on Windows File Servers) with **Azure Files**.

### Key Concepts

- **Azure Files** provides a file share accessible via SMB.
- **Azure File Sync** helps keep on-prem SMB shares in sync with Azure Files.

### Components

- **Sync Group**: Logical container for syncing
- **Server Endpoints**: Registered Windows File Servers (up to 100)
- **Cloud Endpoint**: Azure File Share

### Features

- Keeps multiple file servers synchronized through Azure
- Provides **resiliency** by allowing Azure to serve as a backup
- Integrates with **Azure AD**, **Kerberos**, and **Azure AD DS**

---

## Cloud Tiering

Azure File Sync supports **Cloud Tiering**:

- Automatically offloads **least-used files** to Azure while keeping them accessible via stubs.
- Triggers:
  - **Free space threshold** (e.g., offload when local disk gets full)
  - **Access time threshold** (e.g., offload files not accessed for 60 days)

---

## Azure Storage Explorer

A **GUI tool** for interacting with various Azure Storage types:

- Supports **Blobs**, **Files**, **Queues**, and **Tables**
- Upload/Download:
  - Entire folders or files
  - Queue messages or Table entries
- Great for **one-time or interactive** data transfer

---

## Azure Storage Browser (Portal)

Built into the Azure Portal:

- Similar to Storage Explorer but web-based
- View/upload/download blobs and files
- Manage queues and tables

---

## AzCopy

**Command-line tool** for automation and large-scale data movement.

### Features

- Supports **copying and syncing** data
- Source/destination:
  - Local ↔ Azure
  - Azure ↔ Azure (server-side)
  - AWS/GCP ↔ Azure
- Optimized for **performance and scripting**

---

## Azure Migrate

Used for migrating **VMs and databases** to Azure.

### Supports

- **VMware**, **Hyper-V**, or even **bare metal OS**
- On-prem databases

### Process

1. **Assess** source environment
2. **Recommend** best Azure SKU
3. **Replicate** to Azure
4. **Cutover** workload

---

## Azure Data Box (Offline Migration)

Used when **network bandwidth is insufficient** or data size is too large for online transfer.

### 1. Azure Data Box Disk

- 1–5 encrypted SSDs
- 8 TB each
- **Import-only** (no export)

### 2. Azure Data Box

- Encrypted 80 TB box
- Uses **SMB/NFS**
- **Supports import/export**
- Ships via FedEx/UPS

### 3. Azure Data Box Heavy

- Up to **770 TB**
- Weighs ~500 lbs
- Ships via freight
- Works like Data Box but for **very large datasets**

---

## Summary of Tools

| Tool                | Use Case                                       |
|---------------------|------------------------------------------------|
| **Azure File Sync** | SMB share sync/resiliency/cloud backup         |
| **Cloud Tiering**   | Offload cold data to cloud automatically       |
| **Storage Explorer**| GUI for interactive data uploads/downloads     |
| **Storage Browser** | Web version of Explorer in Azure Portal        |
| **AzCopy**          | CLI for automated and large-scale transfers    |
| **Azure Migrate**   | Move VMs and DBs to Azure with assessment      |
| **Data Box (All)**  | Offline transfer of large datasets             |

---

## Choosing Online vs Offline

- **Online**:
  - Azure File Sync
  - AzCopy
  - Azure Migrate
  - Azure Storage Explorer
- **Offline**:
  - Azure Data Box
  - Azure Data Box Disk
  - Azure Data Box Heavy

---

By understanding these tools, you can efficiently plan and execute data migration strategies that suit your bandwidth, security, scale, and automation needs.
