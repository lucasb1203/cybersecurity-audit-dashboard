personal access token (PAT) :   

8/7 (outline)
          # Week 1 Notes – Cybersecurity Audit + Dashboard Project

## ✅ What I Completed This Week

### 🔍 Project Scope Defined
- Auditing my **personal laptop** running **Ubuntu 22.04**
- Focus: detecting local system threats and real-time visibility
- Scope includes:
  - Monitoring system authentication logs (`/var/log/auth.log`)
  - Scanning for open ports and unusual network activity
  - File integrity monitoring for `/etc` and `/home`
  - Real-time alerting for high-severity events

### 🧰 Tools Selected
- **Wazuh agent** for monitoring & alerting
- **ELK Stack** (Elasticsearch, Logstash, Kibana) for dashboarding
- **Nmap** for port scanning
- **Lynis** for system hardening baseline audit (optional)

### 📂 GitHub Project Setup
- Initialized a local Git repository
- Linked to GitHub: `https://github.com/lucasb1203/cybersecurity-audit-dashboard`
- Created `week1/scope.md` and pushed initial commit
- Learned how to use a Personal Access Token (PAT) for secure GitHub authentication

---

## 🗺️ Plan for Weeks 2–4

### 🔧 Week 2: Asset Discovery + Baseline Audit
- Use `nmap` to scan local device/network and document open ports
- Create `week2/asset_inventory.md` or `.csv` listing:
  - Hostname
  - IP address
  - Open ports
  - Detected services
- Run `lynis` or `chkrootkit` to identify misconfigurations or vulnerabilities

### 📦 Week 3: Logging + Event Collection
- Install and configure **Wazuh agent**
- Forward logs to local ELK stack or Wazuh dashboard
- Set up rules to detect:
  - Failed login attempts
  - Suspicious file access
  - Port scans
- Store configuration notes and screenshots in `week3/`

### 📊 Week 4: Build and Polish the Dashboard
- Create real-time panels in **Kibana**:
  - System alerts
  - Port scan detections
  - Login attempt graphs
- Add screenshots to `week4/` for visual documentation
- Write final summary of findings and lessons learned

---

## 🎯 Final Deliverables
- Working Wazuh/ELK setup with real-time security metrics
- Dashboard panels visualizing live audit data
- Clean GitHub repo with markdown notes, screenshots, and config files
- Optional: a short write-up explaining project value for resume or interviews

---

## 💡 Extra Ideas (if time allows)
- Try alerting via Slack or email using Wazuh rules
- Build a second dashboard using Grafana or Splunk Free
- Compare results from `nmap`, `netstat`, and `ss` for deeper port analysis

8/8 (outline)        
