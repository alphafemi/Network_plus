This covers the critical lifecycle management processes for network hardware and software, including end-of-life (EOL), end-of-support (EOS), patching, firmware updates, decommissioning, change management, and service request tracking. Proper lifecycle management ensures security, stability, and compliance.



---

### Network Lifecycle Management Cheat Sheet

This guide covers the stages of hardware and software lifecycle, update management, secure decommissioning, change control, and service request processes.

---

#### End of Life (EOL) vs. End of Support (EOS)

| Term | Definition | Implications |
| :--- | :--- | :--- |
| **End of Life (EOL)** | Manufacturer announces they will stop selling and eventually stop supporting the product. | No new features; may still receive security patches for a limited time. Time to plan replacement budget and schedule. |
| **End of Support (EOS)** | Manufacturer ceases all updates, including security patches. | **Critical security risk.** No further fixes for vulnerabilities. Device should be replaced immediately or isolated. |

**Best Practice:** Monitor EOL announcements and budget for replacements before EOS occurs.

---

#### Patching and Updates

Updates are essential for security, stability, and compliance.

| Update Type | Description | Examples |
| :--- | :--- | :--- |
| **Operating System (OS) Updates** | Regular patches for Windows, Linux, macOS, iOS, Android. | Monthly "Patch Tuesday" (Microsoft); quarterly service packs. |
| **Security Patches** | Fixes for known vulnerabilities; may be released **out-of-band** for critical zero-day exploits. | Emergency patch outside normal schedule. |
| **Configuration Changes** | Administrative modifications to OS settings. | Password policy changes; firewall rule updates; user permission changes. |
| **Antimalware/Antivirus Updates** | Signature and engine updates for threat detection. | Daily or real-time definition updates. |

**Scheduling:** Many organizations follow a predictable monthly patch cycle, with emergency procedures for critical security updates.

---

#### Firmware Updates

Firmware is the embedded software that runs on purpose-built hardware (printers, switches, routers, cable modems, IoT devices).

| Aspect | Description |
| :--- | :--- |
| **Purpose** | Fix bugs, close security holes, add features, improve stability. |
| **Deployment Methods** | Over the network (remote) or physical connection (console port, USB). |
| **Risk** | Manufacturers vary in firmware quality and update frequency. |
| **Best Practice** | Always have a **rollback plan** and save previous firmware binaries in a secure location. |

**Real-World Example (from video):**
- **Trane Comfortlink thermostats:** Vulnerabilities reported April 2014.
- **Firmware update available:** April 2015 (12 months later).
- **Final fix:** January 2016 (21 months total).
- **Lesson:** Security team must evaluate whether to keep such devices on the network or find alternatives.

---

#### Decommissioning and Media Sanitization

When hardware reaches end of life, proper disposal is critical to protect data.

| Method | Description | When to Use |
| :--- | :--- | :--- |
| **Sanitization** | Securely erase data (e.g., DoD 5220.22-M, cryptographic erase for SSDs). | When hardware will be reused or resold. |
| **Physical Destruction** | Shredding, crushing, incinerating drives. | When data is highly sensitive or sanitization is impractical. |
| **Secure Storage** | Store decommissioned devices in locked, monitored facilities. | When legal hold or retention policies prevent destruction. |

**What NOT to do:**
- Do not dispose of equipment in normal trash.
- Do not discard without data removal.
- Do not sell or donate without proper sanitization.

**Legal Considerations:**
- Some regulations require specific retention periods (e.g., financial records, healthcare data).
- Destruction may be prohibited until retention expires.

---

#### Change Management

Change management is a formal process for planning, approving, testing, and rolling back modifications to IT systems.

| Change Management Step | Description |
| :--- | :--- |
| **1. Request** | Submit proposed change (what, why, when, risk assessment). |
| **2. Review** | Change Advisory Board (CAB) evaluates impact, risk, and schedule. |
| **3. Approval** | Authorized change with defined implementation window. |
| **4. Implementation** | Apply change following documented procedure. |
| **5. Testing** | Verify change worked as expected. |
| **6. Rollback Plan** | Predefined steps to revert if problems occur. |
| **7. Documentation** | Record change details, outcome, and any issues encountered. |

**Why Change Management Matters:**
- Prevents unauthorized or untested changes.
- Provides audit trail for compliance.
- Enables coordination across teams.
- Reduces risk of outages from poorly planned changes.

**Examples of Changes Requiring Management:**
- Upgrading switch/router firmware.
- Modifying firewall rules.
- Changing routing tables.
- Updating OS configurations.

---

#### Service Request Management (Help Desk)

Service request tracking systems manage user-reported issues, maintenance tasks, and service requests.

| Term | Description |
| :--- | :--- |
| **Ticket** | Unique identifier for each request or incident. |
| **Triage** | Prioritizing tickets based on urgency and impact. |
| **Assignment** | Routing ticket to appropriate technician or team. |
| **Resolution** | Fixing the issue and documenting the solution. |
| **Closure** | Confirming resolution with user and closing the ticket. |

**Common Service Request Software:**
- ServiceNow
- Jira Service Management
- Zendesk
- Freshservice
- Request Tracker (RT)

**Key Benefits:**
- Tracks work and accountability.
- Provides metrics (mean time to resolve, ticket volume).
- Enables trend analysis and root cause identification.

---

#### Key Takeaways

| Takeaway | Explanation |
| :--- | :--- |
| **EOL triggers planning; EOS triggers urgency** | End of support means no more security patches—replace or isolate. |
| **Patching is ongoing** | OS updates, firmware updates, and configuration changes must be managed on a regular schedule. |
| **Firmware quality varies** | Some manufacturers are slow to patch; security teams must assess risk and consider alternatives. |
| **Decommissioning must protect data** | Sanitize or destroy media; never discard equipment in regular trash. |
| **Change management prevents chaos** | Formal processes for approval, testing, and rollback reduce risk of outages. |
| **Service request systems track work** | Tickets provide accountability, metrics, and audit trails for support activities. |
