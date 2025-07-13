# Azure IoT Services Overview

## Topic Context

This lesson is part of the **AZ-900 Certification** track and falls under:

* **Describe core solutions and management tools on Azure**
* Focus: **Core solutions available in Azure** → **Internet of Things (IoT)**

Future lessons in this track will cover:

* Big Data
* Machine Learning
* Serverless Compute
* DevOps

---

## What is IoT?

* The **Internet of Things (IoT)** refers to the networking of physical devices embedded with microcontrollers, sensors, and software that connect and exchange data with cloud services.
* Devices today often have built-in microcontrollers but may not be internet-connected or updatable.

**With IoT, devices can:**

* Send data (telemetry) to the cloud
* Receive commands and updates from the cloud
* Communicate with each other

This connectivity allows:

* Firmware updates
* New capabilities
* Remote command execution
* Real-time telemetry monitoring

**Challenges with IoT:**

* Increased attack surface
* Need for secure communication
* Device authentication and identity management
* Risk of false data or impersonation

---

## Azure IoT Services

### 1. Azure IoT Hub

* **Foundation service for IoT communication**
* Enables **Device-to-Cloud** and **Cloud-to-Device** interaction
* Supports:

  * Telemetry data uploads
  * File uploads
  * Commands and control from cloud to device
  * Request-response mechanisms

#### Key Features

* **Device Identity**: Each device has a unique identity

* **Device Twin**: A digital replica of the physical device containing:

  * Current state
  * Desired configurations
  * Pending commands

* Interaction happens with the **Device Twin**, not directly with the physical device

* SDKs provided to build custom applications to manage device communication and workflows

**Use IoT Hub when:**

* You want to build your own custom app
* You need basic communication and telemetry support
* You’re writing your own logic using SDKs

---

### 2. Azure IoT Central

* A **SaaS solution built on top of IoT Hub**
* Provides a **complete, ready-made IoT platform**

#### Features:

* Pre-built **dashboards** and **device templates**
* **Simulated devices** for testing
* **Industry-specific starter apps** (Retail, Healthcare, Energy, etc.)
* **Graphical Rule Engine**:

  * If telemetry meets a **condition**
  * Then trigger an **action** (email, SMS, webhook, Azure Function, Logic App)

#### Key Benefits:

* Quick start with minimal coding
* Customizable templates and workflows
* Suitable for organizations needing fast deployment and visualization

**Use IoT Central when:**

* You need a plug-and-play IoT solution
* You don’t want to write custom backend code
* You want dashboards, alerting, and simulation out-of-the-box

---

### 3. Azure Sphere

* **End-to-end security platform for IoT devices**

#### Components:

1. **Azure Sphere Microcontroller Unit (MCU)**

   * Certified secure hardware licensed by Microsoft
2. **Azure Sphere OS**

   * A custom Linux-based OS maintained by Microsoft
3. **Azure Sphere Security Service (AS3)**

   * Ensures device identity, integrity, and communication security

#### Use Cases:

* When **hardware-level security** is critical (e.g., healthcare, industrial IoT)
* Devices need to prove they’re uncompromised
* Uses **certificate-based authentication** (no passwords)

**Azure Sphere does not replace IoT Hub/Central**, but rather works alongside them to enhance security.

---

## Summary of Azure IoT Services

| Service      | Purpose                                   | Coding Required | Best For                             |
| ------------ | ----------------------------------------- | --------------- | ------------------------------------ |
| IoT Hub      | Communication layer for IoT devices       | Yes             | Custom IoT application development   |
| IoT Central  | SaaS-based, plug-and-play IoT platform    | No              | Quick deployment, industry solutions |
| Azure Sphere | End-to-end hardware + OS + cloud security | No (for user)   | Highly secure IoT deployments        |

These services can be used **individually** or **together**, depending on business needs and security requirements.
