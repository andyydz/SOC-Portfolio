# Investigation with Splunk

Hands-on SOC investigation walkthroughs built inside **Splunk Enterprise Security (ES)**, simulating the day-to-day workflow of an L1 SOC Analyst: triaging alerts from the queue, pivoting through raw events, enriching with asset/identity context, and documenting findings on a timeline.

This folder contains screenshot evidence from two investigation scenarios.

---

##Scenario 1 — Anomalous VPN Connection

**Goal:** Investigate a flagged VPN connection alert surfaced in the Splunk ES Analyst Queue and determine whether it represents legitimate remote access or unauthorized activity.

**Workflow:**
1. **Analyst Queue** – Picked up the notable event from the ES incident review queue.
2. **VPN Connection Search** – Ran an SPL search to pull all VPN authentication events tied to the alert (source IP, user, timestamp, geo/location).
3. **Expanded Event Details** – Drilled into the raw event to review full field data — session duration, auth method, and any related events around the same time window.
4. **Asset & Identity Lookup** – Cross-referenced the source IP/user against asset and identity lookups in ES to confirm whether the device and account matched known, authorized inventory.

**What this demonstrates:** alert triage discipline, SPL query writing, and the habit of *never trusting an alert at face value* — validating identity and asset context before making a verdict.

> *[Verdict: "Alert triaged and investigated. Asset context, VPN activity, and event telemetry were validated. No additional suspicious behavior was identified, and the alert was closed as benign."]*

| Analyst Queue | VPN Connection Search |
|---|---|
| ![Analyst Queue](Screenshots/8-splunk-es-analyst-queue.png) | ![VPN Connection Search](Screenshots/10-vpn-connection-search.png) |

| Expanded Event Details | Asset & Identity Lookup |
|---|---|
| ![Expanded Event Details](Screenshots/11-expanded-event-details.png) | ![Asset Identity Lookup](Screenshots/12-asset-identity-lookup.png) |

---

##Scenario 2 — Suspicious `wevtutil` Execution (Anti-Forensics Indicator)

**Goal:** Investigate a suspicious use of `wevtutil.exe`, a native Windows utility that can be abused to **clear or manipulate Windows Event Logs** — a common technique attackers use to cover their tracks after gaining access.

**Workflow:**
1. **Suspicious Command Detection** – Identified `wevtutil` execution in process/command-line logs, a red flag since it's rarely run by normal users.
2. **Intermediate Findings** – Correlated the command with surrounding endpoint activity to build context around what happened before/after the log-clearing attempt.
3. **Timeline Reconstruction** – Built an event timeline to establish sequence and scope of activity, supporting root-cause and impact analysis.

**What this demonstrates:** recognizing living-off-the-land (LOLBin) techniques, understanding MITRE ATT&CK **T1070.001 (Indicator Removal – Clear Windows Event Logs)**, and the ability to reconstruct attacker activity from fragmented log evidence.

> *[Verdict: "Confirmed suspicious activity. Timeline correlation and process analysis indicated potential defense evasion, warranting escalation to the Incident Response team"]*

| Suspicious `wevtutil` Detection | Intermediate Findings |
|---|---|
| ![Suspicious wevtutil](Screenshots/14-suspisious-wevtutil-investigation.png) | ![Intermediate Findings](Screenshots/16-intermediate-findings.png) |

![Timeline Reconstruction](Screenshots/17intermediate-finfings-timeline.png)
*Timeline Reconstruction*

---

##Skills Demonstrated
- Splunk ES incident review & alert triage
- SPL (Search Processing Language) query writing
- Log correlation and event timeline reconstruction
- Asset & identity enrichment for context-driven decisions
- MITRE ATT&CK mapping (anti-forensics / indicator removal)
- Clear, evidence-based investigation documentation

---

*Part of my [SOC-Portfolio](https://github.com/andyydz/SOC-Portfolio) — a collection of hands-on blue team investigations across Splunk, Elastic (ELK), Wazuh, and Wireshark.*
