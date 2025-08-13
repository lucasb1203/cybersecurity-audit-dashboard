Cybersecurity Audit & Dashboard Project
Objective

To perform a comprehensive security audit of a Linux system, identify vulnerabilities, and build a real-time monitoring dashboard to track authentication attempts, network activity, and configuration changes.
This project simulates a professional endpoint security audit workflow and is being conducted in a Virtual Machine running Ubuntu 22.04 before deploying to a production workstation.
Scope

    Monitor and analyze authentication logs (/var/log/auth.log)

    Scan for open ports and unusual network activity

    Implement file integrity monitoring for /etc and /home

    Enable real-time alerting for high-severity events

    Create a Kibana dashboard displaying key security metrics

Tools & Technologies
Tool	Purpose
Wazuh Agent	Security event collection and alerting
ELK Stack	Log indexing, search, and visualization
Nmap	Network scanning and port auditing
Lynis	System vulnerability assessment
(Optional) File Integrity Monitoring tools	Monitor critical file changes
Timeline & Progress
Week 1 – Planning & Setup

    Defined project scope and deliverables

    Created a week-by-week implementation plan

    Set up GitHub repository for documentation and tracking

    Outlined final deliverables and extra enhancement ideas

Deliverable(s):

    week1/notes.md – Project scope, goals, plan, and deliverables

Week 2 – Baseline Security Audit

    Day 1–2:

        Collected baseline asset inventory (assets_inventory.md)

        Verified SSH connectivity and documented with screenshots

    Day 3:

        Executed Lynis scan for security posture assessment

        Saved raw scan results (lynis_scan_results.txt)

        Documented vulnerabilities, severity levels, and recommended remediation (lynis_findings.md)

        Captured Lynis summary screenshots for evidence

Deliverable(s):

    week2/assets_inventory.md – Inventory of installed packages, services, and system configurations

    week2/lynis_scan_results.txt – Raw Lynis scan data

    week2/lynis_findings.md – Formatted vulnerability analysis

    week2/screenshots/ssh/ – SSH session proof

    week2/screenshots/lynis/ – Lynis scan evidence

Why This Matters

This project reflects practical, hands-on cybersecurity skills in:

    Vulnerability assessment

    Log analysis

    Network security

    Documentation and reporting
    It mirrors workflows in professional Security Operations Centers (SOCs) and IT audit teams, making it directly relevant to entry-level cybersecurity roles.

Planned Final Deliverables (End of Week 4)

    Complete Security Audit Report

    Functional Kibana Dashboard showing:

        Authentication events

        Network anomalies

        File integrity alerts

    Full documentation & evidence

    Remediation plan for discovered vulnerabilities

Next Steps

    Week 3: Install & configure Wazuh + ELK stack, integrate log collection

    Week 4: Build dashboard visualizations, finalize audit report, and migrate project to production system for final testing
