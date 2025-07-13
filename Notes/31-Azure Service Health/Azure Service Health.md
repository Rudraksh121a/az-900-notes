# 🌐 Azure Service Health

## Lesson Overview
In this lesson, we cover the **functionality and usage of Azure Service Health**, which provides a **personalized view of the health of Azure services, regions, and resources**. This is essential for monitoring **service issues, planned maintenance, health advisories, and historical outages**.

---

## Topics to Cover
- Introduction to Azure Service Health
- Navigating the Service Health Portal
- Monitoring:
  - Service Issues
  - Planned Maintenance
  - Health Advisories
  - Security Advisories
- Viewing Health History
- Creating Health Alerts
- Integration with Action Groups

---

## What is Azure Service Health?
Azure Service Health helps you stay informed about:
- Current **service issues** in Azure.
- **Planned maintenance** events.
- **Health advisories** and recommendations.
- **Security-related updates**.
- Historical health events with **Root Cause Analysis (RCA)**.

You can customize it to monitor:
- Specific **regions**
- Specific **services**
- Specific **subscriptions**

---

## Using the Azure Portal

###  Navigation
1. Go to the **Azure Portal**.
2. Scroll down to **"Help and Support"**.
3. Select **"Service Health"**.

---

## Key Features

### 1. **Service Issues**
- Shows real-time information on outages.
- Updates are typically provided **hourly**.
- Includes RCA post-resolution.

### 2. **Planned Maintenance**
- Informs you of upcoming **scheduled changes** that may impact your services.

### 3. **Health Advisories**
- Alerts you about **recommended actions** to maintain or improve resource health.

### 4. **Security Advisories**
- Notifications related to **security vulnerabilities or updates**.

---

## Health History

You can review:
- Up to **3 months of past incidents**.
- Detailed breakdown of:
  - **What happened**
  - **When it was resolved**
  - **Root cause explanations**
  - **Recommended actions** (if any)

---

## Creating Health Alerts

You can configure alerts for:
- Specific **services**
- Specific **regions**
- Event types:
  - Planned maintenance
  - Health advisories
  - Service issues

### Integration:
- Alerts can trigger **Action Groups** (like email, SMS, webhook notifications).

---

## Why Azure Service Health Matters
- Ensures **proactive awareness** of problems.
- Provides **visibility and accountability** during incidents.
- Enables **automated alerting** and **faster response**.

---

## Quick Summary Table

| Feature             | Purpose                                      | Example                               |
|---------------------|----------------------------------------------|----------------------------------------|
| Service Issues       | Track real-time outages                      | VM unresponsive due to Azure region issue |
| Planned Maintenance | Know upcoming scheduled changes              | SQL DB maintenance scheduled tomorrow  |
| Health Advisories    | Get actionable recommendations               | Increase quota for better performance  |
| Security Advisories  | Stay safe with vulnerability alerts          | Patch security risk on Linux VMs       |
| Health History       | Review past issues with RCA                  | Outage on 01-Jan explained in detail   |
| Health Alerts        | Get notified proactively via Action Groups   | Email alert for East US service issue  |

---

## Tip
> Combine **Azure Service Health** with **Azure Monitor** for full-stack operational awareness and automated incident response.

---
