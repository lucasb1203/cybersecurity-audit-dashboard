# Linux Security Baseline Audit (Lynis)  
**System:** Ubuntu 22.04 LTS (VirtualBox VM)  
**Date:** 2025‑08‑12  
**Day 1-3 (Week 2)**
**Tool:** Lynis 3.0.7 (`sudo lynis audit system`)

---

## 1) Executive Summary
- **Hardening Index:** **58 / 100**
- **Audit Scope:** Local host baseline (no container/forensics testing)
- **Overall Posture:** Acceptable for a lab VM; several high‑value hardening tasks pending (patching, firewall rules, audit/logging).

---

## 2) Key Results
| Category | Status |
|---|---|
| Tests Performed | 252 |
| Plugins Enabled | 1 |
| Firewall Present | Yes (iptables) |
| Firewall Rules | **None active** ❗ |
| Malware Scanner | **Not installed** |
| Vulnerable Packages | **Detected** ❗ |

---

## 3) High‑Priority Findings (Action in 24–48h)
| ID | Finding | Evidence | Impact | Remediation (Commands) |
|---|---|---|---|---|
| PKGS‑7392 | Vulnerable / outdated packages | “Found one or more vulnerable packages” | Exploitable software | `sudo apt update && sudo apt upgrade -y && sudo apt autoremove -y` |
| FIRE‑4512 | iptables modules loaded, **no rules active** | Lynis firewall check | No network filtering | Quick allow‑SSH baseline: `sudo ufw allow 22/tcp && sudo ufw enable && sudo ufw status` |

---

## 4) Medium‑Priority Hardening Items
- **Account/Password Policy**
  - Configure password aging & rounds (`/etc/login.defs`):  
    `PASS_MAX_DAYS 90`, `PASS_MIN_DAYS 7`, `PASS_WARN_AGE 14`; enable stronger hashing rounds.
- **SSH Tightening (`/etc/ssh/sshd_config`)**
  - Set:  
    `AllowTcpForwarding no` • `ClientAliveCountMax 2` • `Compression no` • `LogLevel VERBOSE` • `MaxAuthTries 3` • `MaxSessions 2` • `X11Forwarding no`  
    Then: `sudo systemctl restart ssh`
- **Logging/Auditing**
  - Enable **auditd**: `sudo apt install auditd -y && sudo systemctl enable --now auditd`
  - Consider remote log archival (e.g., forward to Wazuh/ELK later in project).
- **File Integrity Monitoring**
  - Install a tool (we’ll integrate Wazuh later). For standalone:  
    `sudo apt install aide -y && sudo aideinit && sudo mv /var/lib/aide/aide.db.new /var/lib/aide/aide.db`
- **CUPS exposure**
  - If printing not needed, disable: `sudo systemctl disable --now cups cups-browsed`

---

## 5) Low‑Priority / Hygiene
- Install helpful Debian tools: `libpam-tmpdir`, `apt-listbugs`, `apt-listchanges`, `needrestart`, `fail2ban`, `debsums`, `apt-show-versions`.
- Consider separate partitions for `/home`, `/tmp`, `/var` (note for non‑VM prod).
- Remove unused protocols (dccp, sctp, rds, tipc) via blacklist if not needed.
- Add legal banners: edit `/etc/issue` and `/etc/issue.net`.

---

## 6) Evidence & Artifacts
- **Raw Output:** `week2/lynis_scan_results.txt`
- **Notable Lines:**  
  - Warnings: PKGS‑7392 (vuln packages), FIRE‑4512 (no firewall rules)  
  - SSH suggestions: AllowTcpForwarding, ClientAliveCountMax, Compression, LogLevel, MaxAuthTries, MaxSessions, TCPKeepAlive, X11Forwarding, AllowAgentForwarding
- **Next Audit Trigger:** After applying High‑Priority items, rerun:  
  `sudo lynis audit system` (expect Hardening Index ↑)

---

## 7) Roadmap Linkage (Project)
- **Week 3:** Stand up Wazuh + forward logs; begin dashboard KPIs (auth failures, sudo use, SSH events, UFW denies).
- **Week 4:** Kibana panels + final screenshots; policy write‑up & comparison of pre/post hardening scores.

---

## 8) Change Log
- 2025‑08‑12: Initial baseline (HI=58). No UFW rules; vulnerable packages present.


