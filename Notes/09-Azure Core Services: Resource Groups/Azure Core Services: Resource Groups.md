# ☁️ Azure Core Services: Resource Groups

## 📌 What Is a Resource Group?

A **Resource Group** is a container that holds related Azure resources.

- Every Azure resource (VM, Storage Account, etc.) must be in **one and only one** resource group.
- It **cannot** be nested inside another resource group.
- Resource Groups exist within **subscriptions**.

---

## 🗺️ Region & Resource Group

- A **Resource Group** has a **region** (for metadata storage only).
- But the resources inside can be from **any region**.

```text
Example:
Resource Group: "DevApp-RG" (Region: East US)
→ Can contain:
   - VM (in West Europe)
   - Storage (in East US)
   - App Service (in Central India)
