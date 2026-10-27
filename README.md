# SOC Portfolio

This repository documents my learning and hands-on progress toward an entry-level Security Operations Center (SOC) Analyst role. It will grow as I complete practical exercises, investigations, and projects.

## Current Learning and Progress

I am developing foundational skills in:

- Cybersecurity fundamentals and hands-on practice through TryHackMe
- Linux and computer networking fundamentals
- Security monitoring, SIEM concepts, and incident response fundamentals
- Introductory practice with tools and concepts such as Wazuh, Splunk, Wireshark, and MITRE ATT&CK

These reflect my learning and practice to date, not a claim of advanced proficiency in every tool.

## Projects

### Bank Secure Network

A Cisco Packet Tracer networking project focused on network topology, VLAN segmentation, and access-control concepts.

Repository: [bank-secure-network](https://github.com/andyydz/bank-secure-network)

### Security Incident & Asset Tracker

A console-based Java, JDBC, and MariaDB application for managing IT assets and tracking security incidents.

Repository: [security-incident-asset-tracker](https://github.com/andyydz/security-incident-asset-tracker)


### [Sentinel — Integrated SOC Lab](https://github.com/andyydz/sentinel-soc-lab)

**Status:** In Progress

An evidence-driven Security Operations Center (SOC) lab built around Wazuh, Linux endpoints, detection engineering, and incident investigation.

**Progress so far:**
- Established communication between the Wazuh manager and Linux endpoint agent.
- Validated File Integrity Monitoring (FIM) using controlled file activity.
- Completed CASE-001 investigation work covering file modification, creation, and deletion.
- Reviewed Wazuh alerts and supporting logs to identify which detection rules triggered.
- Documented investigation findings, screenshots, and detection gaps.

**Key finding:** During CASE-001 validation, built-in Wazuh rules detected file creation and deletion events, while custom rule `100002` did not trigger for those events. This identified an area for further detection engineering and retesting.

**Next steps:** Improve detection coverage, develop additional investigation cases, document response workflows, and measure detection effectiveness.
## Future Portfolio Work

I plan to add more hands-on SOC exercises, detection and investigation write-ups, and supporting evidence as the work is completed. Some folders and files may be preparatory work; their existence does not mean the associated project or exercise is finished.

## Next Phase

My current priority is completing college examinations. After exams, I plan to resume expanding this portfolio, continue developing Sentinel, and assess which additional SOC exercises would add meaningful evidence of practical skills.

## Profiles

- [GitHub](https://github.com/andyydz)
- [TryHackMe](https://tryhackme.com/p/andyydz57)
