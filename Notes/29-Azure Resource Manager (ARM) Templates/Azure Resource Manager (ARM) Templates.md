# Azure Resource Manager (ARM) Templates

## Overview

Azure Resource Manager (ARM) is the deployment and management service for Azure. Every action performed in Azure is managed through ARM and defined using **JSON (JavaScript Object Notation)**.

## Declarative vs Imperative

### Declarative Approach (ARM Template):
- Defines **what** the end state should be.
- Does not describe **how** to achieve it.
- Example: "I want a Storage Account named `sa1`, with locally redundant storage, in East US."

### Imperative Approach (PowerShell / CLI):
- Describes **how** to create each resource.
- Must include every command step.
- Can fail midway and require manual recovery or changes to scripts.

---

## What is an ARM Template?

- A **JSON file** that declares the infrastructure you want to deploy.
- Uses **parameters**, **variables**, and **resource definitions**.
- Can be **version-controlled** (e.g., in Git).
- Can be deployed via:
  - Azure CLI
  - PowerShell
  - Azure DevOps pipelines

### Benefits:
- **Idempotent**: Reapplying the same template doesn’t cause duplication.
- **Declarative**: You focus on the desired state.
- **Repeatable**: Ensures consistency across environments.

---

## ARM Template Example

An example template might:
- Take parameters for resource type and location.
- Define a resource of type `Microsoft.Storage/storageAccounts`.
- Include configuration such as redundancy (`LRS`, `GRS`) and region (`East US`).

### Deployment Scenario:
- Initial deployment creates a Storage Account `sa1` in East US with LRS.
- Re-deploying without changes does nothing.
- If you change redundancy to `GRS`, a redeployment **updates** the storage account accordingly.

---

## Deploying ARM Templates

You can deploy ARM templates using:
- `az deployment group create` (Azure CLI)
- `New-AzResourceGroupDeployment` (PowerShell)
- Azure DevOps pipelines

You can define **multiple resources** in a single template:
- Deployed **in parallel** if there's no dependency.
- **Sequentially** if dependencies exist.

---

## Infrastructure as Code and Version Control

- ARM templates can be stored in Git repositories.
- Enables integration into **CI/CD pipelines**.
- Useful for DevOps workflows and automated deployments.

---

## Bicep - A Simpler Alternative

### What is Bicep?
- A domain-specific language (DSL) for ARM templates.
- Easier and more human-friendly than raw JSON.
- Still **declarative**, but uses a syntax similar to TypeScript.

### How it Works:
- Bicep files are **transpiled** to ARM templates before deployment.
- Same resource providers and deployment mechanisms as ARM templates.

### Example:
- Define parameters and resources with a cleaner, simpler syntax.
- Easier to write and maintain.

---

## Other Tools: Terraform

- Third-party tool with **Azure provider** support.
- Also declarative and suitable for provisioning Azure resources.
- Alternative to ARM templates/Bicep but not native to Azure.

---

## Why Use ARM Templates?

- **Declarative**: State your intent, not execution steps.
- **Repeatable**: Run any number of times without duplication.
- **Trackable**: Store in version control, detect configuration drift.
- **Scalable**: Define and deploy multiple resources in one go.

---

## When to Choose ARM Templates

- Anytime you want to **provision resources in Azure**.
- Best suited for CI/CD and infrastructure-as-code solutions.
- Native, supported, and powerful for Azure resource deployment.

### If a question asks:
**"What technology should be used to provision Azure resources?"**
> The answer is: **ARM Templates**.
