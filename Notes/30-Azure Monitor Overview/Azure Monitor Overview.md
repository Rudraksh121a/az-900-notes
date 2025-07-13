# Azure Monitor Overview

## Introduction

Azure Monitor is a comprehensive solution for collecting, analyzing, and acting on telemetry data from Azure environments. It helps you understand the performance and health of your resources and applications.

---

## Types of Monitoring Data

### 1. **Azure AD Logs**
- Includes:
  - Audit logs
  - Sign-in logs
  - Risk logs
- Retention depends on the Azure AD plan (e.g., 7 days for free, 30+ for P1/P2).

### 2. **Azure Subscription Logs**
- Activity logs related to Azure Resource Manager (ARM).
- Retained for **90 days** by default.

### 3. **Resource-Level Telemetry**
- Two types:
  - **Metrics** (enabled by default)
  - **Logs** (optional via diagnostic settings)

---

## Azure Monitor Architecture

### Metrics
- Stored in a **time-series database**.
- Collected by default.
- Accessible via the Azure Monitor portal for visualizations.

### Logs
- Not enabled by default.
- Requires **Diagnostic Settings** to configure what logs to capture and where to send them.

---

## Diagnostic Settings: Log Destinations

Logs can be sent to the following targets:

### 1. **Azure Storage**
- Best for **retention** and archival.
- Not useful for analytics.

### 2. **Event Hub**
- Used to send logs to **external systems** (e.g., SIEM solutions).

### 3. **Log Analytics Workspace**
- Core component for querying and analyzing logs.
- Supports retention up to **2 years**.
- Charges based on **ingested data** and **retention period**.

You can configure metrics and logs to go to these destinations based on your requirements.

---

## Azure Monitor Workspaces

- Centralized hub for managing all monitoring data.
- **Log Analytics Workspace** is now integrated with Azure Monitor.
- Solutions like **Insights**, **Azure Sentinel**, and others build on top of this.

---

## Viewing Metrics

- Accessible via the **Azure Portal** under the “Monitor” section.
- Metrics are numeric, time-based data like:
  - CPU usage
  - Blob storage capacity
- Can be viewed at both resource-level and via Azure Monitor dashboards.

---

## Alerts in Azure Monitor

### Alert Rules
- Triggered based on:
  - Metrics
  - Logs
  - Activity logs
- Can generate alerts visible in:
  - Azure Portal
  - Azure Mobile App

### Action Groups
- Define **automated responses** to alert triggers.
- Possible actions:
  - Email or SMS
  - Webhook
  - Call Azure Function or Logic App
  - Integrate with ITSM tools
  - Trigger Event Hub or Automation Runbooks

### Alert Processing Rules
- Used to filter or suppress alerts.
- Helps manage large-scale environments and prevent alert fatigue.

---

## Summary

Azure Monitor is a powerful and flexible monitoring platform that:

- Collects and stores **metrics and logs**.
- Visualizes resource performance and usage.
- Sends data to:
  - Azure Storage
  - Event Hub
  - Log Analytics
- Enables **alerting** and **automated responses**.
- Supports integrations with **Azure Sentinel**, **Insights**, and external tools.

### Key Takeaway:
> Use Azure Monitor to get centralized visibility and control over your Azure environment's health and performance, with deep integration and automation capabilities.
