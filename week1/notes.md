# Cybersecurity Audit + Dashboard Project – Week 1 Notes  
**Date:** 2025-08-07  
**Day 1–7 (Week 1)**  
**GitHub Repository:** [https://github.com/lucasb1203/cybersecurity-audit-dashboard](#)

---

## 1) Project Overview
Auditing a personal Ubuntu 22.04 LTS system (running in a VirtualBox VM) to detect unauthorized access, monitor configuration changes, and visualize security alerts.

**Why this matters:**  
This project demonstrates the ability to set scope, select appropriate tools, and follow a structured workflow with weekly deliverables — all of which are critical skills for a cybersecurity professional.

---

## 2) Scope
- Monitor `/var/log/auth.log` for authentication events.
- Detect unusual network activity (e.g., open ports).
- File integrity monitoring for `/etc` and `/home`.
- Real-time alerting for high-severity events.

---

## 3) Tools
- **Wazuh Agent**
- **ELK Stack** (Elasticsearch, Logstash, Kibana)
- **Nmap**
- **Lynis** (baseline audit)
- *Optional:* Fail2Ban, AIDE

---

## 4) Week-by-Week Breakdown

| Week | Goal | Deliverables |
|------|------|--------------|
| **Week 1** | Scope & Planning | `notes.md`, scope, deliverables list |
| **Week 2** | Asset Inventory + Baseline Audit | `asset_inventory.md`, `lynis_findings.md`, raw scan outputs, screenshots |
| **Week 3** | Wazuh Setup & Dashboard Integration | Config files, Wazuh-Kibana dashboards |
| **Week 4** | Final Hardening + Presentation | Before/after metrics, final report, `README.md` |

---

## 5) Final Deliverables
- Structured report with evidence.
- GitHub repository with raw + formatted findings.
- Screenshots showing before/after improvements.

---

## 6) Extra Ideas
- Compare results across different OS builds.
- Automate scanning with cron jobs.
- Add email alerting for high-severity Wazuh events.



