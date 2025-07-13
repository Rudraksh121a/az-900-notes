# Azure Cost Management

Azure Cost Management helps you both **analyze** and **control** your cloud spending.

---

## 1. Cost Analysis

### Purpose
- Understand where and how your money is being spent.
- Visualize current and forecasted Azure costs.

### Features
- **Subscription-based breakdown** of cost usage.
- **ML-based forecasting** to estimate end-of-month spending.
- **Breakdowns by**:
  - Service type
  - Region/location
  - Resource groups
  - Tags (e.g., Cost Center)

### Grouping Options
- Group cost data by tag, resource type, service, location, etc.
- Example: Group by `Cost Center` to see departmental expenses.

### View Options
- Accumulated costs
- Daily costs
- Cost by resource type
- Detailed line items for full billing transparency

---

## 2. Budgets

### Purpose
- Set spending limits and trigger alerts or actions when thresholds are crossed.

### How it Works
- Define a **scope** (e.g., entire subscription).
- Use **historical spending** to decide budget values.
- Apply **filters** like:
  - Resource type
  - Tag
  - Reservation name

### Budget Configuration
- Set budget name, amount (e.g., $200), time period, and expiration.
- Two budget alert types:
  1. **Actual Spend** — Trigger alerts/actions when a % of actual spend is hit (e.g., 50%, 100%).
  2. **Forecasted Spend** — Trigger based on predicted future usage trends.

### Actions
- Send alert emails.
- Trigger **Azure Monitor Action Groups** (e.g., webhook, Azure function, automation).

---

## Summary

Azure Cost Management helps with:
- **Cost visibility** via customizable analysis tools.
- **Cost control** through proactive budgets and alerts.
- Enables businesses to track, forecast, and manage their cloud expenses efficiently.
