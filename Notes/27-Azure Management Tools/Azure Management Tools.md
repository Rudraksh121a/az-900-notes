# Azure Management Tools

## Overview

In this lesson, we explore the **functionality of various Azure management tools** and how they interact with **Azure Resource Manager (ARM)**.

---

## Tools Covered

- Azure Portal
- Azure PowerShell
- Azure CLI
- Azure Cloud Shell
- Azure Mobile App

> All tools ultimately interact with **Azure Resource Manager (ARM)** for management operations.

---

## 1. Azure Portal

- **Graphical, web-based interface**.
- Very intuitive and easy to navigate.
- Good for:
  - Viewing and monitoring resources.
  - Investigating configuration and metrics.

### Pros:
- Discoverability of services.
- Visual dashboards and metrics.

### Cons:
- **Slow** for resource creation.
- Hard to maintain **consistency** across environments.
- Poor at **scaling** or documenting exact steps.
- Not suitable for mass operations or automation.

---

## 2. Azure Mobile App

- Available on **iOS** and **Android**.
- Limited functionality:
  - Basic alerts.
  - Starting/stopping services.
- Not designed for full-scale resource management or creation.

---

## 3. Scripting Tools

### a. Azure PowerShell

- **Cross-platform**: Available on Windows, Linux, macOS.
- Uses `Az` PowerShell module.
- Ideal for users familiar with PowerShell and want to **automate tasks** using **imperative** scripting.

```powershell
Get-AzVM | Format-Table
