# 🔁 Incident Response Simulation — Phishing (Controlled & Authorized)

## Overview
This repository documents a controlled **Phishing Simulation & Incident Response** exercise performed in an authorized lab environment.  
The simulation was designed to evaluate detection, escalation, containment, and recovery processes and to measure user awareness and SIEM/endpoint detection effectiveness.


## Table of Contents
- [Objectives](#objectives)  
- [Scope & Authorization](#scope--authorization)  
- [Environment & Tools](#environment--tools)  
- [Simulation Design](#simulation-design)  
- [Execution Steps](#execution-steps)  
- [Detection & Triage](#detection--triage)  
- [Containment, Eradication & Recovery](#containment-eradication--recovery)  
- [Metrics & Results](#metrics--results)  
- [Deliverables](#deliverables)  
- [Key Recommendations](#key-recommendations)  
- [Ethics & Legal](#ethics--legal)  
- [Contact](#contact)

---

## Objectives
- Validate detection capability across email gateway, SIEM, and endpoint logs.  
- Test incident escalation and operational readiness.  
- Measure user behavior (clicks vs reports) and improve awareness.  
- Produce actionable remediation and training guidance.

---

## Scope & Authorization
- **Scope:** Simulated emails delivered to a small, consented user group and lab test endpoints only.  
- **Authorization:** Written approval obtained from relevant stakeholders before execution.  
- **Boundaries:** No production systems targeted; no credential harvesting; no destructive payloads used.

---

## Environment & Tools
- Email test environment (internal SMTP or phishing platform for simulations)  
- Windows endpoints with Sysmon + EDR/AV logging enabled  
- SIEM (Splunk or equivalent) for event collection and correlation  
- Wireshark / packet captures (for offline analysis)  
- Host-only or isolated lab network

---

## Simulation Design
- **Phishing vector:** A benign, realistic-looking email prompting users to open an internal training PDF (no credential requests).  
- **Goal:** Measure click-through rate, reporting rate, and the time-to-detect/contain.  
- **Safety:** All links point to internal lab resources or non-malicious files.

**Example (safe) email subject:** `Mandatory: Security Awareness Update — Please read`

---

## Execution Steps
1. Obtain written authorization and define the target group.  
2. Prepare benign phishing email template and internal hosting for reference file.  
3. Send simulation emails to consented participants.  
4. Monitor detection channels: email gateway logs, SIEM, Sysmon, and EDR.  
5. Triage alerts, identify affected hosts/users, and collect evidence (logs, timelines, pcaps).  
6. Execute containment (isolate hosts), eradicate test artifacts, recover systems from snapshots if required.  
7. Produce a post-sim report and run targeted awareness training for clickers.

---

## Detection & Triage
- **Data sources used:** email gateway logs, SIEM correlation searches, Sysmon EventID 1 (Process Create), endpoint telemetry.  
- **Triage outputs:** list of impacted hosts and users, relevant process IDs and timestamps, and correlation of click events to endpoint activity.  
- **Typical indicators:** URL click events, subsequent process creation, unusual network connections to lab hosts.

---

## Containment, Eradication & Recovery
- **Containment:** Isolate affected host(s) from the network, block test URLs at perimeter gateway.  
- **Eradication:** Remove test files, clean artifacts, and run full AV/EDR scans.  
- **Recovery:** Restore clean snapshots or validate host cleanliness, re-enable accounts, and monitor for recurrence.

---

## Metrics & Results (Sample)
- Delivered: 50 emails  
- Clicked: 6 → Click-Through Rate (CTR) = 12%  
- Reported: 18 → Reporting Rate = 36%  
- Mean Time to Detect (MTTD): 45 minutes  
- Mean Time to Contain (MTTC): 30 minutes

> These metrics are examples — replace with actual numbers from your simulation.

---

## Deliverables
- `README.md` (this file)  
- `phishing_email_template.txt` — safe template used for the exercise  
- `playbook_IR_phishing.md` — step-by-step IR playbook for phishing incidents  
- `post_sim_report.pdf` — executive summary with metrics and recommendations (redacted)  
- `evidence_summary.csv` — redacted timeline of affected hosts/users

---

## Key Recommendations
1. Improve email gateway filtering and URL reputation checks.  
2. Add SIEM correlation rules for email-click → process creation sequences.  
3. Increase user reporting via micro-trainings and simulated reward programs.  
4. Run quarterly phishing simulations and update playbooks accordingly.

---

## Ethics & Legal
- Simulation conducted with written authorization and limited scope.  
- No actual credentials were captured or exfiltrated.  
- All findings were handled confidentially and used to improve security posture.

---

## Contact
- GitHub: https://github.com/Nazakat-12
- LinkedIn: https://www.linkedin.com/in/nazakat-ali-a808982a2/

---

**License & Use:** This repository is for educational and authorized testing purposes only. Do not use the contents on systems you do not own or have explicit permission to test.
