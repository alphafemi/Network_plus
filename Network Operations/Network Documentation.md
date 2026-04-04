


---

### Network Documentation Cheat Sheet

This guide covers the different types of network documentation, their purposes, and best practices for maintaining them.

---

#### Network Diagrams

| Diagram Type | Focus | What It Shows | Use Case |
| :--- | :--- | :--- | :--- |
| **Physical Network Map** | Hardware & cabling | Physical layout of equipment, cable runs, port connections, device locations. | Troubleshooting physical connectivity; locating specific cables or devices. |
| **Logical Network Map** | High-level connectivity | How networks connect (e.g., WAN cloud connecting HQ to branches); IP subnets; routing relationships. | Planning new locations; understanding traffic flow; high-level architecture reviews. |
| **Rack Diagram** | Physical rack layout | Front/back view of racks with units (U) labeled; shows exact placement of servers, switches, PDUs. | Remote troubleshooting; instructing on-site staff which device to reboot. |
| **Cable Map** | Building cabling infrastructure | Paths of cables under floors/above ceilings; drop locations and numbering; IDF/MDF termination points. | Installation; troubleshooting specific drops; planning moves/adds/changes. |

**Common Diagramming Software:**
- Microsoft Visio
- OmniGraffle (macOS)
- Gliffy (web-based)
- Lucidchart
- Draw.io (free)

---

#### Combined Layer Diagrams

A single diagram can overlay Layer 1, Layer 2, and Layer 3 information for a comprehensive view.

| Layer | Information Shown |
| :--- | :--- |
| **Layer 1 (Physical)** | Interface names (e.g., Gi0/1), cable types, port numbers. |
| **Layer 2 (Data Link)** | MAC addresses, VLAN assignments, trunk ports. |
| **Layer 3 (Network)** | IP addresses, subnet masks, routing protocols, default gateways. |

**Benefit:** Correlates physical ports with MAC addresses and IP addresses in one view—invaluable for troubleshooting.

---

#### Asset Management

Asset tracking involves labeling every piece of hardware (laptops, servers, routers, switches, firewalls) and maintaining a centralized database.

| Asset Tag Information | Purpose |
| :--- | :--- |
| **Unique ID (barcode/RFID)** | Identifies the device in trouble tickets and inventory systems. |
| **Purchase date** | Tracks depreciation; determines warranty status. |
| **Assigned user** | Links device to a person for location tracking and accountability. |
| **Location** | Physical location (building, rack, room) for field service. |
| **Warranty expiration** | Knows when support contracts end. |
| **Software/license info** | Tracks installed software for license compliance and audits. |

**Cross-Departmental Uses:**
- **IT Support:** Trouble ticket referencing asset #42.
- **Accounting:** Depreciation schedules.
- **Finance:** Warranty validation.
- **Procurement:** License count verification.

---

#### IP Address Management (IPAM)

IPAM is a centralized system for planning, tracking, and managing IP address space (both IPv4 and IPv6).

| IPAM Feature | Description |
| :--- | :--- |
| **Subnet management** | View all subnets, utilization, and available addresses. |
| **DHCP integration** | Shows which devices received which IPs at which times (forensic value). |
| **History/logging** | Change logs, error logs, warning logs for IP configuration changes. |
| **Capacity planning** | Identifies address shortages; suggests when to add new scopes. |
| **Central console** | Manages IPv4 and IPv6 addressing across the entire organization from one interface. |

**Why IPAM Matters:**
- Dynamic IP addressing (DHCP) makes it hard to know who used which IP when.
- IPAM logs provide a historical record for troubleshooting and security investigations.

---

#### Service Level Agreement (SLA)

An SLA is a contract between an organization and a service provider (ISP, WAN carrier, cloud provider) that defines the minimum acceptable level of service.

| SLA Component | Example |
| :--- | :--- |
| **Uptime guarantee** | 99.99% availability (≈ 52 minutes of downtime per year). |
| **Maximum unscheduled downtime** | No more than 4 hours per incident. |
| **Response time** | 15-minute response to trouble ticket; 4-hour on-site dispatch. |
| **Remedies** | Service credits, expedited hardware replacement. |
| **Exclusions** | Scheduled maintenance windows, acts of God, customer-caused outages. |

**Purpose:** Provides a contractual basis for holding providers accountable and recovering costs when service levels are not met.

---

#### Site Survey and Heat Maps

A **site survey** documents the wireless environment, identifying all access points (both owned and third-party) and their frequencies.

| Documentation | Description |
| :--- | :--- |
| **Site Survey** | Systematic measurement of wireless signal strength, interference, and channel usage across a facility. |
| **Heat Map** | Visual representation (color-coded overlay on floor plan) showing signal strength by location. |

**Heat Map Colors (typical):**
- **Green / Red:** Strong signal.
- **Yellow / Orange:** Moderate signal.
- **Blue / Purple:** Weak or no signal.

**Use Cases:**
- Planning AP placement (new installs).
- Troubleshooting dead zones.
- Identifying interference from neighboring networks.
- Re-surveying after changes to building layout or wireless environment.

**Frequency of Site Surveys:** In dense environments (e.g., multi-tenant buildings, large campuses), surveys should be performed regularly as neighboring networks change.

---

#### Key Takeaways

| Takeaway | Explanation |
| :--- | :--- |
| **Physical vs. logical diagrams serve different purposes** | Physical = cables/ports; Logical = high-level connectivity. |
| **Rack diagrams enable remote support** | Document exact U positions so remote staff can locate equipment. |
| **Cable maps are essential for IDF/MDF** | Shows which desk drops correspond to which patch panel ports. |
| **Asset tracking links hardware, user, location, and warranty** | Central database supports IT, accounting, and procurement. |
| **IPAM logs DHCP history** | Critical for forensic analysis and capacity planning. |
| **SLAs hold providers accountable** | Contractually defined uptime and response guarantees. |
| **Site surveys + heat maps optimize wireless** | Identify dead zones and interference; plan AP placement. |
