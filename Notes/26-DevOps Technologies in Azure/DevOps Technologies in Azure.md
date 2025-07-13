# DevOps Technologies in Azure

## 1. What is DevOps?

- **DevOps** is not just a tool—it's a **process**, **approach**, and **mindset**.
- It emphasizes **collaboration**, **automation**, and **continuous improvement** across development and operations.

### Key Concepts:
- **Continuous Integration (CI)**
- **Continuous Delivery (CD)**
- **Continuous Deployment**
- **Version control with Git and Git repositories**

---

## 2. Azure DevOps Overview

### Main Components:

#### a. Repos
- Version-controlled source code management.
- Primarily uses **Git**.
- Previously supported **Team Foundation Version Control (TFVC)** (legacy).
- Enables team collaboration through code sharing and synchronization.

#### b. Boards
- Used for **project management** and tracking work items.
- Supports:
  - **Kanban boards**
  - **Swimlanes** (e.g., High Priority, Regular, Fun Fridays)
  - **WIP (Work-In-Progress) limits**
- Tracks:
  - **Epics**
  - **Features**
  - **User Stories**
  - **Tasks**
- Enables sprint planning, backlogs, and tracking development workflows.

#### c. Pipelines
- Enables **CI/CD**:
  - Automatically tests and builds code as it is committed.
  - Supports deployment across multiple environments.
- Supports:
  - **Cloud or self-hosted agents**
  - **Gates and approvals** (conditions for progressing through pipeline stages)

#### d. Artifacts
- Stores compiled assets or packages for reuse in builds or deployments.

---

## 3. GitHub as a DevOps Platform

### Key Features:

#### a. GitHub Repositories
- Focused purely on **Git-based version control**.
- Excellent for **code hosting**, **collaboration**, and **code security**.
- Uses AI to scan for:
  - Security vulnerabilities
  - Secrets or keys in code

#### b. GitHub Actions
- Event-driven workflows (beyond just CI/CD).
- Triggers include:
  - Pull requests
  - Issue creation
  - Member joining
- Supports **custom workflows** using YAML.
- Offers **environment definitions** with conditional gates for deployment.

#### c. GitHub Projects
- Provides **basic Kanban-style boards**.
- Still evolving—less powerful than Azure DevOps Boards, but under **active development**.

---

## 4. Choosing Between Azure DevOps and GitHub

| Feature         | Azure DevOps                         | GitHub                               |
|----------------|--------------------------------------|--------------------------------------|
| Version Control | Git, TFVC (legacy)                  | Git only                             |
| Boards          | Advanced project management         | Basic Kanban support                 |
| Pipelines       | Mature CI/CD pipelines              | GitHub Actions (flexible triggers)   |
| Artifacts       | Built-in support                    | Not native (requires external setup) |
| Investments     | Slower development focus            | Active development & feature growth  |

### Recommendation:
- Use **GitHub** for new projects due to future-focused investment.
- Existing Azure DevOps setups can continue using pipelines and boards.
- Integration between GitHub and Azure DevOps is possible.

---

## 5. Azure DevTest Labs

- Dedicated service for **on-demand development/testing environments**.
- Use cases:
  - Testing across multiple platforms and configurations.
- Key Benefits:
  - Create environments with ARM templates.
  - Automatically **delete resources** after testing to reduce cost.
  - Not limited to VMs—any Azure resource is supported.

---

## 6. Summary of DevOps in Azure

| Service            | Purpose                                  |
|--------------------|-------------------------------------------|
| **Azure DevOps**   | Legacy DevOps suite with mature tools     |
| **GitHub**         | Git-centric modern DevOps platform        |
| **DevTest Labs**   | Temporary environments for testing builds |

- DevOps is a **practice**, not just tooling.
- Azure supports DevOps workflows with a wide array of services depending on the need and maturity of the team.

