
---

### **Week 2 – `lynis_findings.md`** (Reformatted & Cleaned)
```markdown
# Lynis Security Audit – Week 2 Day 3  
**Date:** 2025-08-12  
**GitHub Repository:** [https://github.com/lucasb1203/cybersecurity-audit-dashboard](#)

---

## 1) Executive Summary
- **Hardening Index:** 58 / 100  
- **Tests Performed:** 252  
- **Overall Posture:** Acceptable for a VM lab environment; several high-priority remediations pending.

---

## 2) High-Priority Findings
| Finding ID | Description | Impact | Remediation |
|------------|-------------|--------|-------------|
| PKGS-7392 | Outdated/vulnerable packages | Exploitable software | `sudo apt update && sudo apt upgrade -y` |
| FIRE-4512 | No active firewall rules | Unfiltered network access | `sudo ufw allow 22/tcp && sudo ufw enable` |

---

## 3) Medium-Priority Recommendations
- Strengthen SSH configuration (`/etc/ssh/sshd_config`).
- Enable auditd for advanced logging.
- Configure password policy (`/etc/login.defs`).

---

## 4) Why this matters
Running a baseline audit with Lynis identifies system weaknesses before they are exploited. Remediating these findings will directly increase the hardening index and overall security posture.

---

## 5) Evidence
- **Raw Scan Output:** [lynis_scan_results.txt](./lynis_scan_results.txt)  
- **Screenshots:**  lynis_scan_p(1-4).png screenshots

---

## 6) Next Steps
- Apply high-priority remediations within 48h.
- Re-run Lynis to confirm score improvement.
- Forward logs to Wazuh for correlation in Week 3.

