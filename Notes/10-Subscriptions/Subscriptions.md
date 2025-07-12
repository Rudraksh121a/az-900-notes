#  Azure Fundamentals: Subscriptions

##  What Is a Subscription?

A **Subscription** is the **base unit of agreement** between a customer and Microsoft.

- It's a **billing boundary** (e.g., Pay-As-You-Go, Enterprise Agreement).
- It's a **security boundary** (by default).
- Every Azure deployment must occur **within a subscription**.

---

## Key Characteristics

| Feature                    | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| Billing Boundary           | Charges are tracked per subscription                                        |
| Security Trust Boundary    | Role-based access control (RBAC) begins here                                |
| Linked to Azure AD         | Each subscription **trusts only one Azure Active Directory (AD) tenant**    |
| Multiple Subscriptions     | Organizations can create multiple subscriptions as needed                   |

---

##Azure AD & Subscriptions

- Subscriptions **trust one and only one Azure AD tenant**.
- Azure AD contains:
  - Users
  - Groups
  - Devices
- Azure AD is **separate** from the subscription, but used for **identity and RBAC**.

```text
Example:
Subscription A → Trusts Azure AD Tenant X
Subscription B → Can trust Azure AD Tenant Y (if moved)
