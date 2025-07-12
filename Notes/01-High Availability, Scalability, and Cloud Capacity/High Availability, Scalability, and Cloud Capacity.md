# Azure Fundamentals: High Availability, Scalability, and Cloud Capacity

## 1. What is Cloud Computing?

> “There’s no cloud – it’s just someone else’s PC.”  
This reflects the idea that cloud computing uses remote servers (owned by cloud providers) to offer scalable services.

### Key Cloud Capabilities
- **Capacity**: Compute, storage, and networking.
- **Management**: Azure Portal, APIs, CLI.
- **User Experience**: Web interfaces, SDKs, and services.

### On-Premises Setup
- Physical servers and network infrastructure.
- High upfront cost, static capacity.
- Always-on costs regardless of actual usage.

### In the Cloud
- Massive, on-demand capacity managed by providers (e.g., Azure).
- Pay-as-you-go billing model.
- Services scale instantly and globally.

---

## 2. Azure Global Infrastructure

### Key Terms
- **Region**: Group of data centers (e.g., Central India, East US).
- **Availability Zone**: Physically separate DCs within a region for fault isolation.
- **Data Center**: Physical site housing servers, storage, and networking.

### Flexibility Benefits
- Deploy services close to users (reduced latency).
- Distribute workloads across regions for resilience.
- Access to hundreds of services: VMs, AKS, SQL, AI/ML, and more.

---

## 3. Benefits of the Cloud

### Agility
- Deploy, resize, or remove resources quickly.
- Switch services (e.g., VM → Container → App Service).
- Per-second billing (pay only for what is used).

### Example
- Scale from 4-core VM to 8-core VM.
- Move services between regions instantly.

---

## 4. High Availability (HA)

### Definition
Ability of a system to remain operational despite failures.

### Azure Support
- Each resource has a Service Level Agreement (SLA).
- Architect solutions to meet required SLA targets.

### HA Strategy
- Use **multiple instances** across failure boundaries:
  - Servers
  - Racks
  - Data Centers
  - Availability Zones

### Blast Radius
- The extent of failure caused by an issue (e.g., server, rack).
- Reduce impact by distributing instances across zones.

---

## 5. Disaster Recovery (DR)

### Definition
Process to restore service after catastrophic failures (e.g., natural disasters).

### DR Architecture
- Use regions **hundreds of miles apart**.
- Combine with one of the following:
  - Backup & Restore
  - Geo-redundant replication
  - Active-active deployments

### Key Metrics
- **RTO (Recovery Time Objective)**: How fast service should be restored.
- **RPO (Recovery Point Objective)**: Maximum acceptable data loss.

---

## 6. Scalability and Elasticity

### Definitions
- **Scalability**: Ability to increase or decrease resource capacity.
- **Elasticity**: Automatically adjusting resources based on load/demand.

### Types of Scaling

#### 1. Vertical Scaling (Scale Up/Down)
- Increase size (CPU, RAM) of a single instance.
- Requires restart → causes downtime.
- Not redundant or HA-friendly.

#### 2. Horizontal Scaling (Scale Out/In)
- Add/remove instances dynamically.
- No downtime.
- Load balancers distribute traffic.
- Supports HA and elasticity.

---

## 7. Real-World Use Cases of Scaling

| Use Case           | Load Pattern                   | Cloud Scaling Benefit            |
|--------------------|--------------------------------|----------------------------------|
| Tax Filing App     | Peak once a year               | Auto-scale only during peak      |
| Food Delivery App  | Peak during evenings/weekends  | Elastic scale in/out             |
| Olympics Streaming | Huge spike every 4 years       | Regional DR + horizontal scaling |

---

## Summary Checklist

| Concept             | Key Points                                                            |
|---------------------|------------------------------------------------------------------------|
| Cloud Capacity       | Global, on-demand, scalable infrastructure                            |
| Agility              | Quick deployments, easy migrations, per-second billing                |
| High Availability    | Multiple instances across failure zones                               |
| Disaster Recovery    | Cross-region resiliency with RTO/RPO planning                         |
| Vertical Scaling     | Bigger instance = downtime + poor HA                                  |
| Horizontal Scaling   | Add/remove instances = no downtime + best for HA                      |
| Elasticity           | Match real-time workload automatically or on schedule                 |

---


