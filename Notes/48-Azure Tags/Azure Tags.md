# Azure Tags

This lesson focuses on the **functionality and usage of Azure Tags**, which help in managing, organizing, and classifying resources using metadata.

---

## 1. What Are Tags?

- **Tags** are metadata in the form of **key-value pairs**.
- They are used to categorize and logically organize Azure resources.
- Tags can be applied to:
  - Subscriptions
  - Resource Groups
  - Individual Resources

---

## 2. Characteristics of Tags

- Tags are:
  - Not inherited (unlike resource locks or RBAC).
  - **Directly applied** to the specific level (resource, group, or subscription).
- Example:
  - Tag Key: `Environment`
  - Tag Value: `Production`

---

## 3. Inheritance and Azure Policy

- Tags do **not inherit** from parent scopes by default.
- To **automatically assign or enforce tags**, you must use **Azure Policy**.
- Azure Policy can:
  - Require specific tags.
  - Automatically apply tags based on parent scope.
  - Deny resource creation if tags are missing (use with caution).

---

## 4. Use Cases for Tags

Tags can be used for various business and operational purposes, such as:

- **Cost Management**
  - Example: `CostCenter = Finance`
- **Environment Classification**
  - Example: `Environment = Dev`, `Test`, `Prod`
- **Ownership**
  - Example: `Owner = Rudraksh`
- **Security/Compliance**
  - Example: `Compliance = GDPR`
- **Operating System**
  - Example: `OS = Windows 11`

---

## 5. How to Apply Tags

Tags can be applied using:

- **Azure Portal**
- **ARM templates**
- **Azure PowerShell**
- **Azure CLI**
- **Azure REST APIs**

---

## 6. Example Workflow (Azure Portal)

- Navigate to a resource (e.g., Virtual Machine).
- Go to the **"Tags"** section.
- Add tags like:
  - `Environment = Dev`
  - `Owner = Rudraksh`
  - `OS = Windows 11`
- Save changes.

---

## 7. Using Tags for Management

- Tags are searchable and filterable across Azure.
- You can:
  - Filter resources by tag (e.g., `OS = Windows 11`)
  - Use tags in Azure Cost Management for **billing reports**
  - Apply governance and compliance via tag-based policies

---

## 8. Best Practices

- Define a **standard tag naming convention** for your organization.
- Keep tag keys and values **consistent**.
- Use **Azure Policy** to enforce critical tags on all resources.
- Avoid excessive tagging that could cause confusion or overhead.

---

## 9. Key Takeaways

- Tags provide powerful metadata for organizing and managing Azure resources.
- They do not affect resource functionality, but are important for:
  - Governance
  - Billing
  - Automation
  - Compliance
- Use Azure Policy to manage tag compliance at scale.

---

This concludes the lesson on **Azure Tags**.
