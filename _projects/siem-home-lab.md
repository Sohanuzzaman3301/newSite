---
tag: LAB-001
title: "SIEM Home Lab — Wazuh + Suricata + Sysmon"
image: "https://picsum.photos/seed/siem-lab/600/400"
description: "3-VM SOC lab on isolated NAT — Wazuh FIM, Suricata IDS, 15+ attacks mapped to 20+ MITRE ATT&CK techniques."
tech: "Wazuh · Suricata · Sysmon · Kali"
github: "https://github.com/Sohanuzzaman3301/SIEM_Home_Lab"
writeup: ""
---
Built 3-VM SOC lab (Wazuh manager, Sysmon endpoint, Kali attacker) on isolated NAT network. Deployed File Integrity Monitoring across system folders with real-time alerting and tuned custom Wazuh rules.

Simulated 15+ attack scenarios (Hydra brute-force, PowerShell, Nmap) and mapped detections to 20+ MITRE ATT&CK techniques. Configured Suricata IDS and built dashboards for alert triage and incident investigation.

**What you see:** topology diagram, Wazuh rule YAML, Suricata config, dashboard screenshots.

**Learned:** Wazuh rule tuning, Suricata IDS deployment, MITRE mapping for analyst workflows.
