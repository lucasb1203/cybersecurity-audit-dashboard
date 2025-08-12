# Lynis Security Audit – Findings (Week 2, Day 3)

**Date:** 2025-08-12  
**System:** Ubuntu 22.04 LTS (VM)  
**Tool:** Lynis 3.0.7  
**Audit Mode:** Normal (Security Audit + Vulnerability Scan)

---

## 📊 Summary
- **Hardening Index:** 58 / 100  
- **Tests Performed:** 252  
- **Plugins Enabled:** 1  
- **Firewall Detected:** Yes  
- **Malware Scanner Installed:** No

---

## ⚠️ Warnings (High Priority Issues)
1. **Found vulnerable packages** – Review and update with:
   ```bash
   sudo apt update && sudo apt upgrade
