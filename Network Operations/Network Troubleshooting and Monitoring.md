This  covers the essential tools and techniques for network troubleshooting and monitoring, including device discovery (LLDP/CDP), traffic analysis (firewall logs, NetFlow, SNMP), availability monitoring, and configuration management. These methods help network professionals identify problems, understand normal behavior, and maintain consistency across devices.


---

### Network Troubleshooting and Monitoring Cheat Sheet

This guide covers the methods for discovering devices, analyzing traffic, monitoring availability and performance, and managing configuration files.

---

#### Device Discovery Protocols

These protocols help identify neighboring devices and build a map of the network.

| Protocol | Full Name | Description | Vendor |
| :--- | :--- | :--- | :--- |
| **LLDP** | Link Layer Discovery Protocol | IEEE standard (802.1AB) for discovering neighboring devices and their capabilities. | Multi-vendor (open standard) |
| **CDP** | Cisco Discovery Protocol | Cisco-proprietary protocol for discovering directly connected Cisco devices. | Cisco (only) |

**What These Protocols Reveal:**
- Device ID (hostname)
- IP address
- Port identifier (which port the neighbor is connected to)
- Capabilities (switch, router, phone, etc.)
- Platform (hardware model)

**Use Case:** When you find an unlabeled cable, LLDP/CDP can tell you what device is on the other end and which port it's connected to.

---

#### Network Scanning and Discovery

| Method | Description | Information Gathered |
| :--- | :--- | :--- |
| **Ping Scan (ICMP)** | Send ICMP echo requests to a range of IP addresses. | Which IP addresses are responding (host is up). |
| **Port Scan (e.g., Nmap)** | Probe IP addresses for open TCP/UDP ports. | Open ports, running services, OS fingerprinting. |
| **SNMP Walk** | Query all OIDs on a device via SNMP. | Detailed device information (interfaces, uptime, CPU, etc.). |
| **Commercial Network Scanners** | Automated tools (e.g., SolarWinds, PRTG, Lansweeper). | Full inventory, device types, software versions. |

**Scanning Cadence:**
- **Daily scans:** Build a historical view of what devices are on the network.
- **On-demand scans:** Troubleshoot a specific issue.

---

#### Traffic Analysis

Traffic analysis provides detailed visibility into what is actually crossing the network.

| Source | Information Provided |
| :--- | :--- |
| **Firewall Logs** | Timestamp, protocol (TCP/UDP), source IP, destination IP, port number, bytes transferred. |
| **NetFlow** | Flow summaries (who talked to whom, when, how much). |
| **Protocol Analyzer (Wireshark)** | Full packet details (headers, payload, retransmissions). |
| **SNMP** | Interface utilization, error counters, CPU/memory. |

**Firewall Log Example Fields:**
| Field | Example |
| :--- | :--- |
| Timestamp | 07:49:38 |
| Protocol | TCP |
| Source IP | 192.168.1.100 |
| Destination IP | 198.51.100.5 |
| Source Port | 54321 |
| Destination Port | 443 (HTTPS) |
| Bytes | 12,456 |

**Use Cases:**
- Identify which applications are consuming bandwidth.
- Detect unusual traffic patterns (potential security incident).
- Troubleshoot specific communication between two hosts.

---

#### Availability Monitoring

The simplest and most critical metric: is the device up or down?

| Status | Meaning | Action |
| :--- | :--- | :--- |
| **Green (Up)** | Device responding to pings or SNMP queries. | Normal operation. |
| **Red (Down)** | Device not responding. | Alert: open ticket, notify on-call, initiate troubleshooting. |

**Monitoring Capabilities:**
- **Real-time view:** Dashboard showing current status of all devices.
- **Historical reports:** Uptime percentage over days, weeks, months (e.g., 99.99% availability).
- **Alerting:** Email, SMS, helpdesk ticket, or integration with SIEM.

**Note:** Availability monitoring only tells you if a device is reachable. To understand *why* it's down or *how* it's performing, you need deeper metrics (SNMP, NetFlow, logs).

---

#### Configuration Management

Configuration files on switches, routers, firewalls, and servers must be managed, backed up, and tracked for changes.

| Task | Description |
| :--- | :--- |
| **Backup Configurations** | Save running config to a secure repository (TFTP server, version control, or management system). |
| **Restore Configurations** | Reload saved config after a failure or when reverting a change. |
| **Firmware/Software Version Compatibility** | Older config files may not load on newer software versions. Keep both configs and firmware binaries. |
| **Configuration Comparison** | Compare configs across identical devices (e.g., 10 web servers) to detect drift or misconfigurations. |
| **Change Detection** | Monitor config files; alert if an unauthorized change occurs. Integrate with change management process. |

**Best Practices:**
- Store config backups in a version-controlled repository (Git, or network management system).
- Tag each config backup with device hostname, date, and software version.
- Automate config backups (daily or after every approved change).
- Test restore procedures regularly.

---

#### Integration with Change Management

Configuration monitoring should be integrated with your organization's change management process.

| Scenario | Action |
| :--- | :--- |
| Authorized change (with ticket number) | Configuration change is expected; no alert or only informational log. |
| Unauthorized change (no ticket) | Raise alert; investigate; potentially revert configuration. |

**Why This Matters:**
- Prevents configuration drift.
- Detects unauthorized or accidental changes.
- Provides audit trail for compliance (PCI, HIPAA, SOX).

---

#### Key Takeaways

| Takeaway | Explanation |
| :--- | :--- |
| **LLDP/CDP reveal neighboring devices** | Essential for understanding physical topology and unlabeled cables. |
| **Scans discover what's on the network** | Ping scans, port scans, and SNMP walks build an inventory. |
| **Traffic analysis provides detail** | Firewall logs, NetFlow, and packet captures show exactly what is crossing the network. |
| **Availability monitoring is the first alert** | Up/down status with real-time dashboards and alerting. |
| **Configuration backups are critical** | Store configs with version and firmware info; enable restore and comparison. |
| **Config change detection enforces change management** | Alerts on unauthorized changes; integrates with approval workflows. |
