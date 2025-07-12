# Azure Networking: Public vs Private Endpoints

## 🔹 Overview

In Azure, services like Storage Accounts can expose two types of network access endpoints:

- **Public Endpoint** – Accessible over the internet
- **Private Endpoint** – Uses a private IP from a Virtual Network (VNet)

---

## 🔹 Public Endpoints

### Characteristics

- Internet-routable address
- Can be accessed from anywhere with proper **authentication**
- Can be restricted using:
  - **IP-based firewall rules**
  - **Virtual Network rules (via Service Endpoints)**

### 🔸 Service Endpoints

- A Service Endpoint allows a **subnet** in a VNet to access a public endpoint securely.
- Still uses the public endpoint but **limits access** to a **known subnet**.

#### Example Configuration

1. Navigate to:  
   `Storage Account > Networking > Firewalls and virtual networks`
2. Select:  
   `Selected networks`
3. Add:
   - Allowed **IP ranges**
   - Allowed **VNets/subnets** using Service Endpoints

> 🔐 You still need authentication (e.g., Azure AD or shared access signature)

---

## 🔹 Private Endpoints

### Characteristics

- Creates a **NIC** in a specified subnet of a VNet
- Assigns a **private IP** from that subnet
- Accesses the Azure service **privately**, not over the internet
- Works with:
  - Local VNet
  - Peered VNets
  - On-premises networks via **VPN** or **ExpressRoute**

### Benefits

- Fully private traffic path
- Can **disable public endpoint** entirely
- DNS integration available using **Azure Private DNS Zones**

### Private Endpoint Configuration

1. Go to:  
   `Storage Account > Networking > Private Endpoint Connections`
2. Click: `+ Add Private Endpoint`
3. Choose:
   - **Service type** (e.g., blob, file)
   - **VNet and subnet**
   - Enable **Private DNS integration**
4. Azure assigns an **internal IP** (e.g., `10.10.0.4`)  
5. DNS resolution is handled automatically to point FQDN to internal IP

> 📝 DNS name stays the same (`mystorage.blob.core.windows.net`)  
> but resolves to the private IP internally

---

## 🔹 DNS Considerations

- Required for TLS/SSL: DNS name must match certificate
- Use **Private DNS Zones** to manage name resolution for private endpoints

---

## 🔹 Summary Comparison

| Feature               | Public Endpoint                          | Private Endpoint                        |
|-----------------------|-------------------------------------------|-----------------------------------------|
| Network Type          | Internet                                  | VNet private IP                         |
| Access Scope          | Public + VNet                             | Only inside VNet or connected network   |
| Restriction Options   | IP Firewall, Service Endpoints            | NSG + DNS + VNet boundaries             |
| Authentication        | Required (Azure AD, SAS)                  | Required                                |
| DNS Name              | Resolves to public IP                     | Resolves to private IP                  |
| Encryption Support    | Yes (TLS/SSL with public DNS name)        | Yes (DNS alias to private IP)           |
| Internet Disabled     | ❌ Optional                                | ✅ Possible                              |

---

## 🔹 Use Cases

- **Public Endpoint**: General workloads needing global access with firewall rules
- **Private Endpoint**: Secure workloads (e.g., finance, healthcare) needing isolated network access

---

## 🔹 Related Azure Services Supporting Private Endpoints

- Azure Storage (Blob, File, Queue, Table)
- Azure SQL Database
- Azure Key Vault
- App Services (with VNet integration)
- Azure Cosmos DB
- Azure Web Apps
