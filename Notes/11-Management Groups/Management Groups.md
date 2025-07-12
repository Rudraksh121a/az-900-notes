# Azure Fundamentals: Management Groups

## What Are Management Groups?

Management Groups in Azure help organize **multiple subscriptions** into a hierarchical structure for **centralized governance**.

- Subscriptions are linked to an **Azure AD tenant**.
- Management groups allow applying **policies**, **RBAC**, and **budgets** across **many subscriptions at once**.
- Useful when dealing with **dozens or hundreds of subscriptions**.

---

## Key Characteristics

| Feature                      | Description                                                       |
|-----------------------------|-------------------------------------------------------------------|
| Root Management Group       | Automatically created for every Azure AD tenant                   |
| Hierarchy Depth             | Up to 6 levels of management groups (excluding root & subscriptions) |
| Scope Inheritance           | Permissions and policies applied at higher levels flow down       |

---

## Hierarchy Overview

