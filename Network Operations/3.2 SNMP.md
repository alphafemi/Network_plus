This  provides a comprehensive overview of **Simple Network Management Protocol (SNMP)** , a foundational tool for monitoring network devices. It covers how SNMP works, the different versions (v1, v2c, v3), the structure of the Management Information Base (MIB) and Object Identifiers (OIDs), and the difference between polling and traps.



---

### SNMP (Simple Network Management Protocol) Cheat Sheet

This guide covers the purpose, architecture, versions, and components of SNMP for network monitoring.

---

#### SNMP Overview

SNMP is a protocol designed to provide a standardized management interface for network devices (routers, switches, firewalls, servers, printers), regardless of manufacturer.

| Aspect | Description |
| :--- | :--- |
| **Purpose** | Monitor device health, gather statistics (bandwidth, errors, CPU), and receive alerts. |
| **Ports** | **UDP 161** – Polling (manager queries device). <br> **UDP 162** – Traps (device sends unsolicited alerts to manager). |
| **Architecture** | Central **Network Management Station (NMS)** polls devices; devices respond with data. |

---

#### SNMP Versions

| Version | Features | Security | Status |
| :--- | :--- | :--- | :--- |
| **SNMPv1** | Original version; basic polling and MIB access. | **None** – Community strings sent in cleartext. | Obsolete / Avoid. |
| **SNMPv2 / v2c** | Improved efficiency (bulk transfers), more data types. | **None** – Community strings still in cleartext. | Common but insecure. |
| **SNMPv3** | Adds authentication, integrity, and encryption (AES, DES). | **Username + password** (hashed); encrypted payload. | **Recommended** for production. |

**Community Strings (v1/v2c only):**
- Act as simple passwords for access.
- **Read-only (e.g., "public"):** Allows querying data but not changing configuration.
- **Read-write (e.g., "private"):** Allows configuration changes (use with caution).
- **Trap string:** Used for receiving traps.

---

#### SNMP Components

| Component | Full Name | Description |
| :--- | :--- | :--- |
| **MIB** | Management Information Base | A structured database on the managed device containing all measurable parameters (e.g., interface counters, system uptime). |
| **OID** | Object Identifier | A unique numeric address that identifies a specific variable within the MIB (e.g., `1.3.6.1.2.1.1.3.0` = system uptime). |

**OID Structure Example:**
```
1.3.6.1.2.1.1.3.0
│ │ │ │ │ │ │ └─ Instance
│ │ │ │ │ │ └─ Uptime
│ │ │ │ │ └─ System
│ │ │ │ └─ MIB-2
│ │ │ └─ Internet
│ │ └─ DoD
│ └─ Org
└─ ISO
```

**MIB-2 Standard:** A standardized set of OIDs that are identical across devices from all manufacturers. Covers common parameters like interface statistics, IP routing, system description.

**Enterprise-Specific MIBs:** Manufacturers define their own OIDs for device-specific features (e.g., temperature sensors, custom ASIC stats). These require loading the manufacturer's MIB file into the NMS.

---

#### Polling vs. Traps

| Method | Direction | Description | Port |
| :--- | :--- | :--- | :--- |
| **Polling (Get/GetNext)** | NMS → Device | NMS actively queries devices at regular intervals (e.g., every 5 minutes). | UDP 161 |
| **Trap** | Device → NMS | Device sends unsolicited alert to NMS when a predefined threshold is crossed. | UDP 162 |

**Polling Use Case:** Collecting ongoing metrics (bandwidth utilization, error rates) for trend analysis and graphs.

**Trap Use Case:** Instant notification of critical events (link down, high CRC errors, temperature warning).

**Example Workflow:**
- Poll every 5 minutes for normal statistics.
- Configure a trap to send an alert immediately when CRC errors exceed 5 per second.

---

#### SNMP Tools and Data Collection

| Tool Type | Function |
| :--- | :--- |
| **MIB Browser / MIB Walker** | Queries all available OIDs on a device and displays their values. Useful for discovery and testing. |
| **SNMP-based Graphing (e.g., Cacti, PRTG, Zabbix)** | Collects polled data over time and generates graphs for trend analysis (response time, errors, throughput). |
| **Network Management System (NMS)** | Central console that polls devices, receives traps, alerts operators, and stores historical data. |

---

#### Security Recommendations

| Best Practice | Reason |
| :--- | :--- |
| **Use SNMPv3** | Provides encryption, authentication, and integrity—essential for production networks. |
| **Avoid SNMPv1/v2c** | Community strings are sent in cleartext; easily sniffed. |
| **Change default community strings** | Never use "public" or "private" in production. |
| **Use read-only where possible** | Minimizes risk of unauthorized configuration changes. |
| **Restrict SNMP access** | Use firewall rules to allow SNMP only from authorized management stations. |

---

