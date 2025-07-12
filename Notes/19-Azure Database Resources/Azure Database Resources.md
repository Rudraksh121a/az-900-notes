# Azure Database Resources - Notes

## Overview

- Databases are used for **durable, persistent data** storage.
- Databases help extract **insight** from data using queries and analytics.
- Managing OS or database software is not a differentiator; companies focus on **apps and data**.
- Azure offers **managed database services (PaaS)** to reduce operational overhead.

---

## Types of Database Offerings

### 1. **SQL Server-Based Solutions (Relational)**

#### **SQL Server**
- Microsoft's relational DBMS.
- Uses **tables with fixed schemas**, **rows (records)**, and **columns (attributes)**.
- Supports **primary keys** and **foreign keys** for **data normalization**.
- Ideal for structured data with defined relationships.

#### **Azure SQL Database**
- Fully managed PaaS solution.
- Offers **various SKUs** for scalability and features.
- Best for new cloud-native applications.

#### **Azure SQL Managed Instance (SQL MI)**
- Also PaaS but deployed in **your own virtual network**.
- Provides high compatibility with **on-prem SQL Server**.
- Supports advanced features like:
  - Common Language Runtime (CLR)
  - Cross-database queries and transactions
  - SQL Server Agent
  - Distributed partition views

> Use SQL MI when migrating apps that rely on SQL Server-specific features.

---

### 2. **Open Source Relational Databases**

Azure supports managed services for popular open-source databases:

#### **MySQL**, **PostgreSQL**, and **MariaDB**
- Fully managed with:
  - Built-in backups
  - High availability
  - Performance scaling
  - Monitoring
- Best when migrating existing apps with minimal code changes.

#### **PostgreSQL Hyperscale (with Citus)**
- Provides **horizontal scaling** via **sharding** (splitting data across multiple servers).
- Useful for large-scale PostgreSQL workloads.
- Supports:
  - Distributed tables
  - Reference tables replicated across nodes

---

### 3. **Cosmos DB (NoSQL)**

#### Key Features:
- **Born in the cloud**, fully managed, globally distributed.
- **Multi-model** and **multi-API** database.
- Supports multiple **consistency levels**:
  - Strong
  - Eventual
  - Session
  - Bounded staleness
  - Consistent prefix

#### Data Models Supported:
- **Document model**: Uses formats like JSON (API: SQL, MongoDB)
- **Column-family**: Ideal for columnar data (API: Cassandra)
- **Key-Value**: Simple key/value pairs (API: Table)
- **Graph**: Stores relationships (API: Gremlin)

#### Use Case:
- Ideal for cloud-native, high-availability, schema-less applications with global distribution and flexible data models.

---

## Summary Use Cases

| Scenario | Recommended Solution |
|----------|----------------------|
| New SQL-based cloud app | Azure SQL Database |
| Migrating legacy SQL Server with full compatibility | Azure SQL Managed Instance |
| Existing MySQL/PostgreSQL/MariaDB app | Azure Database for MySQL/PostgreSQL/MariaDB |
| Large-scale PostgreSQL workload | PostgreSQL Hyperscale |
| New NoSQL cloud app with flexible data models | Cosmos DB |
