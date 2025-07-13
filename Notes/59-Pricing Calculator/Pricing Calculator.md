# Azure Pricing Calculator and Total Cost of Ownership (TCO) Calculator

## 1. Azure Pricing Calculator

### Purpose
- Helps estimate the cost of Azure services **before deployment**.
- Based on inputs like service type, configuration, and usage.

### Key Inputs
- **Region** of deployment
- **Operating System** (Windows/Linux)
- **Instance type and count**
- **Usage time** (full-time or hours/month)
- **Reserved instance option**
- **Disk types** (OS and data disks)
- **Redundancy, disk size, and type**
- **Storage accounts and managed disks**
- **Transaction costs**
- **Internet egress bandwidth** (varies by region)

### Usage
- Add all planned services to build a full architecture cost estimate.
- Modify configurations based on actual workload usage.
- Export, share, or save the estimate.
- Add support plans and licensing options.

---

## 2. Total Cost of Ownership (TCO) Calculator

### Purpose
- Compares **on-premises vs Azure** costs.
- Helps justify the cloud migration from a business standpoint.

### Key Inputs
- Number of **on-premises workloads** (VMs, storage, databases, network)
- Hardware specs (cores, memory)
- **Licensing models**
- **Geo-redundancy** (GRS) and VM type (e.g., B-series for burstable VMs)
- **Electricity and labor costs**
- **Current software costs** and other assumptions

### Output
- Compares **current (on-premises)** cost with **projected Azure cost**.
- Calculates **estimated savings** over a specified time (e.g., 5 years).
- Allows tweaking of region, assumptions, and licensing.

---

## Summary

- **Pricing Calculator** is used for **Azure service cost estimation**.
- **TCO Calculator** is used to evaluate **overall financial benefit** of moving to Azure.
- These tools are critical for **budgeting, forecasting, and business justification** of Azure solutions.
