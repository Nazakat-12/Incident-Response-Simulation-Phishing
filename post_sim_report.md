#  Post-Simulation Executive Report — Phishing Exercise

**Simulation:** Phishing Awareness Simulation (Authorized)  
**Scope:** [e.g., 50 consented users; internal lab endpoints only]  
**Prepared by:** Nazakat Ali

---

## Executive Summary
A controlled phishing simulation was conducted to evaluate the organization’s detection, escalation, and user awareness. The exercise validated monitoring pipelines and identified improvements in SIEM correlation and user reporting practices.

---

## Key Metrics (Replace with actual results)
- Emails Delivered: **[50]**  
- Clicked (CTR): **[6] (12%)**  
- Reported to Security: **[18] (36%)**  
- Mean Time to Detect (MTTD): **[45 minutes]**  
- Mean Time to Contain (MTTC): **[30 minutes]**

---

## Observations
- Most users who clicked were from [department(s)] and clicked during [time window].  
- SIEM successfully correlated several click events to process creation (Sysmon EventID 1), but some clicks were only visible via proxy logs (gap in email gateway telemetry).  
- EDR detected suspicious process activity on [N] host(s) enabling quick containment.

---

## Top 5 Findings & Impact
1. **Email gateway did not block lab URL by default** — increased exposure to click-through (Operational Risk).  
2. **SIEM correlation rule gap** — lack of automated correlation for email-click → endpoint process creation (Detection Risk).  
3. **User reporting rate moderate (36%)** — awareness program works but needs targeting (Human Risk).  
4. **Endpoint telemetry gaps** — some hosts lacked full Sysmon/EDR coverage (Visibility Risk).  
5. **Playbook execution effective** — containment decision/steps executed within MTTC.

---

## Recommendations (Prioritized)
1. **Implement SIEM correlation rule:** Detect email-click followed by endpoint process creation within 10 minutes. (Owner: Security Ops; ETA: 2 weeks)  
2. **Enhance gateway filtering:** Block known suspicious URL patterns and require URL scanning. (Owner: Network Team; ETA: 1 month)  
3. **Roll out targeted micro-training:** Focus on departments with higher CTR. (Owner: HR/Security Awareness; ETA: 2 weeks)  
4. **Ensure full endpoint telemetry:** Install Sysmon baseline config + EDR on all managed endpoints. (Owner: IT Ops; ETA: 1 month)  
5. **Quarterly simulation cadence:** Run focused phishing tests and tabletop exercises. (Owner: CISO Office; ETA: Ongoing)

---

## Next Steps
- Present findings to stakeholders in a 30-minute briefing.  
- Implement high-priority SIEM rule and re-run a scoped test to validate improvements.  
- Update IR playbook with runbook for email-click incidents.

---

## Appendix
- Evidence package: `evidence_summary.csv` (redacted)  
- Playbook: `playbook_IR_phishing.md`  
- Email Template: `phishing_email_template.txt`

---

