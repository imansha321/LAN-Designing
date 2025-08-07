# ENTC Department Network Design – Cisco Packet Tracer

This project implements a departmental network for the Electronics and Telecommunication (ENTC) department using **Cisco Packet Tracer**. The network is designed for scalability, performance, and security using proper Layer 2 and Layer 3 switching concepts.

---

## 📁 Project Overview

The network consists of:

- **Core Layer 3 Switch** for inter-VLAN routing and DHCP services
- **Access Layer 2 Switches** for end-device connectivity
- **VLAN segmentation** for logical separation of traffic
- **Inter-switch EtherChannel** for redundancy and bandwidth aggregation
- **DHCP & ACL configurations** to manage IP addressing and secure traffic

---

## 📡 Network Architecture

### 🔗 Inter-Switch Connectivity

- Each access switch connects to the Layer 3 core switch via **two 1 Gbps copper links**
- Links are combined using **EtherChannel**, resulting in:
  - **Increased bandwidth (2 Gbps)**
  - **Redundancy in case one link fails**

---

### 💻 End Device Connectivity

- End-user devices (PCs, Laptops, IoT Nodes) are connected via **100 Mbps FastEthernet**
- Sufficient for standard internal communication

---

## 🧩 VLAN Configuration

To enhance **performance**, **management**, and **security**, the network is segmented into VLANs:

| VLAN ID | Name     | Subnet             | Purpose                 |
|---------|----------|--------------------|-------------------------|
| 10      | WIFI     | 192.168.1.0/24     | Wireless Devices        |
| 20      | Labs     | 192.168.2.0/24     | Laboratory Computers    |
| 30      | Security | 192.168.3.0/24     | CCTV Cameras            |
| 40      | Office   | 192.168.4.0/24     | Office Admin Devices    |

Each access switch has ports assigned to appropriate VLANs.

---

## 🔁 Inter-VLAN Routing

- Implemented on the **Layer 3 Core Switch**
- Configured using **Switch Virtual Interfaces (SVIs)**:
  - Each VLAN has a dedicated SVI with the respective gateway IP
  - Enables inter-VLAN communication where permitted

---

## 🧠 DHCP Configuration

- **DHCP Pools** are configured per VLAN on the Core Switch
- Automatically assigns IP addresses to clients within each subnet

---

## 🔐 Access Control & Security

Implemented using **Extended ACLs** on the core switch:

- **Only VLAN 40 (Office)** can access **VLAN 30 (Security)**
- **All other VLANs** are **denied access** to VLAN 30 for enhanced security

---

## ⚙️ Technologies Used

- Cisco Packet Tracer (simulation)
- Layer 2/3 Switching
- VLANs and SVIs
- DHCP Configuration
- EtherChannel (LACP)
- Extended Access Control Lists (ACLs)

---


## 🧪 How to Use

1. Open `entc.pkt` in Cisco Packet Tracer
2. Start simulation mode to test DHCP, inter-VLAN communication, ACL rules
3. View switch/router configurations via CLI to learn setup details



