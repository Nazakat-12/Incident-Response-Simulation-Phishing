#  Phishing Incident Response Playbook (Authorized Simulation)

**Purpose:** Step-by-step actions to detect, triage, contain, eradicate, recover, and report on phishing incidents. Use only in authorized, consented testing environments.

**Alignment:** NIST Incident Response (Preparation → Detection & Analysis → Containment, Eradication & Recovery → Post-Incident Activity)

---

## 1. Preparation (Before Simulation)
- Obtain written authorization and define scope, target group, and allowed actions.
- Notify IT/EDR teams of planned window (if stealth test is not required).
- Create snapshots/checkpoints of endpoints for recovery.
- Whitelist lab hosts/IPs in proxy/gateway & monitoring tools as needed.
- Pre-configure SIEM dashboards and correlation searches to capture:
  - Email gateway logs (delivery, clicks)
  - Sysmon/EDR events (Process Create, Network Connection)
  - DNS and web proxy logs

---

## 2. Detection & Analysis (During Simulation)
**Goals:** Quickly identify clicks, affected hosts, and suspicious endpoint behavior.

**Data Sources:**
- Email gateway logs (delivery, click events)
- SIEM correlation rules
- Sysmon EventIDs (common):
  - EventID 1 — Process Create
  - EventID 3 — Network Connection
  - EventID 11 — File Create
- EDR telemetry and Windows Event Logs
- DNS and proxy logs
- Packet captures (pcap) for network context

**Initial Triage Steps:**
1. Query email gateway for click events and recipients.
2. Use SIEM to map click timestamps to Sysmon/EDR events (process creation, suspicious network calls).
3. Produce a short triage table:
   - User, Hostname, Time, Clicked URL, Observed Process(es), SIEM alert IDs

**Safe example SIEM conceptual search:**
