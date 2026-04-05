This  covers the essential concepts of **Disaster Recovery Planning (DRP)** , including key metrics (RTO, RPO, MTTR, MTBF), site resiliency options (cold, warm, hot sites), and testing methodologies (validation tests, tabletop exercises). These are critical for ensuring business continuity after a significant outage or disaster.


---

### Disaster Recovery and Business Continuity Cheat Sheet

This guide covers the metrics, site types, and testing methods used in disaster recovery planning.

---

#### Disaster Recovery Plan (DRP)

A DRP is a documented plan covering every aspect of how to respond to and recover from a significant outage or disaster that could affect organizational goals.

| DRP Components | Description |
| :--- | :--- |
| **Backups** | On-site and off-site backups of data. |
| **Offsite Data Replication** | Real-time or near-real-time copying of data to a remote location. |
| **Cloud Alternatives** | Stand up servers in cloud environments instead of on-premises. |
| **Remote Site** | Fully operational secondary location to move operations. |
| **Third-Party Contracts** | Agreements for temporary facilities or recovery services. |

---

#### Recovery Metrics

These metrics help define the scope and targets for disaster recovery.

| Metric | Full Name | Definition | Goal |
| :--- | :--- | :--- | :--- |
| **RTO** | Recovery Time Objective | The **amount of time** between the disaster declaration and the restoration of normal service levels. | As close to zero as possible. |
| **RPO** | Recovery Point Objective | The **amount of data loss** measured in time. How far back in time you go when recovering data. | As close to zero as possible (depends on backup frequency). |
| **MTTR** | Mean Time to Repair | The **average time** required to repair or replace a failed component. | Lower is better. |
| **MTBF** | Mean Time Between Failures | The **average time** a device operates before failing. | Higher is better (indicates reliability). |

**RTO vs. RPO Timeline:**
```
Backup/Replication Point          Outage Occurs          Services Restored
        |                              |                        |
        v                              v                        v
[---Data---]==================[---Outage---]=========[--Recovery--]
        |                              |                        |
        v                              v                        v
   RPO (data lost)                RTO (time to restore)
```

**Example Values:**
- **RTO = 1 hour:** Web server must be back online within 1 hour of failure.
- **RPO = 1 hour:** At most 1 hour of data loss is acceptable.
- **MTBF = 20 years:** Firewall expected to run 20 years between failures.
- **MTTR = 30 minutes:** Average time to replace failed router.

---

#### Site Resiliency Types

When moving operations from a primary site to a disaster recovery site, the level of preparation determines how quickly you can resume operations.

| Site Type | Equipment | Data | People | Cost | Recovery Speed |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Cold Site** | Empty building; no equipment. | On backup tapes (must be transported). | Must be transported to site. | Lowest | Slowest (days to weeks) |
| **Warm Site** | Some infrastructure (racks, power, maybe some hardware). | Backup tapes or some replicated data. | May need some transport. | Medium | Moderate (hours to days) |
| **Hot Site** | Exact replica of primary data center hardware. | Real-time or near-real-time replication. | Staff may already be present or easily moved. | Highest | Fastest (minutes to hours) |

**Cold Site Example:** An empty warehouse with power and network drops. You bring your own hardware and backup tapes after a disaster.

**Hot Site Example:** A fully equipped secondary data center with identical servers, storage, and network gear, continuously synced with the primary site.

---

#### DR Testing Methods

Testing ensures the DRP works and that staff know their roles.

| Test Type | Description | Cost/Impact | Purpose |
| :--- | :--- | :--- | :--- |
| **Full Validation Test** | Actual failover to DR site; may take systems offline. | High (people, time, potential disruption) | Validate entire process under real conditions. |
| **Tabletop Exercise** | Team sits around a conference table and walks through a disaster scenario verbally. | Low (meeting time only) | Identify gaps in procedures and logistics without disrupting production. |

**Tabletop Exercise Example:**
- Scenario: "A fire destroys the primary data center building."
- Each department describes what they would do: IT restores from backups, facilities secures alternate space, communications notifies stakeholders.
- Identify what's missing: Do we have current offsite backups? Who has keys to the cold site?

**Full Validation Example:**
- Actually power down primary systems, redirect traffic to hot site, run operations from DR site for a day, then fail back.
- Typically performed annually or semi-annually by organizations with high availability requirements (banks, hospitals, cloud providers).

---

#### MTBF vs. MTTR in DR Planning

| Metric | Impact on DR Plan |
| :--- | :--- |
| **High MTBF** | Device is reliable; you may need fewer spares (e.g., one spare for 100 routers). |
| **Low MTBF** | Device fails frequently; keep multiple spares on hand; consider replacement technology. |
| **Low MTTR** | Device can be repaired quickly; you may not need a full hot spare (just a replacement part). |
| **High MTTR** | Device takes a long time to repair; keep a spare unit ready to swap in. |

---

#### Key Takeaways

| Takeaway | Explanation |
| :--- | :--- |
| **RTO = time to restore service** | How quickly you must be back up after an outage. |
| **RPO = data loss window** | How much data you can afford to lose (drives backup frequency). |
| **MTBF = reliability** | Average time between failures; higher is better. |
| **MTTR = repairability** | Average time to fix; lower is better. |
| **Cold site = cheap but slow** | Empty building; you bring everything after a disaster. |
| **Warm site = moderate cost/speed** | Some infrastructure ready; you bring data and maybe some hardware. |
| **Hot site = expensive but fast** | Exact replica; near-instant failover. |
| **Tabletop exercises validate plans** | Low-cost way to identify gaps in procedures. |
| **Full validation tests prove readiness** | High-cost but essential for mission-critical systems. |
