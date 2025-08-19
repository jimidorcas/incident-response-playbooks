# Incident Response Playbook – Phishing Email  
**Organisation:** Tata  
**Incident Type:** Phishing Attack  
**Framework Reference:** NIST SP 800-61 – Computer Security Incident Handling Guide

---

## 1. Purpose
Provide a structured and repeatable response procedure for handling phishing email incidents within Tata to minimise data loss, credential compromise and operational disruption.

---

## 2. Trigger (Detection Events)
- User reports a suspicious email via the “Report Phishing” button or forwarding to phishing@tata.com  
- SIEM alert (e.g., “High-risk URL clicked” or “Credential harvesting detected”)  
- Anti-spam / email gateway flags a malicious attachment or suspicious sender

---

## 3. Initial Triage and Analysis
| Action | Owner |
|-------|-------|
| Review email headers, URL links and metadata | SOC Analyst |
| Check if user clicked the link / opened attachment | SOC Analyst |
| Inspect affected user’s endpoint for IOCs | Endpoint Engineer |
| Identify common targets or multiple recipients | Incident Handler |

---

## 4. Containment
- Disable access to phishing URL via proxy/URL filtering
- Force password reset for affected user accounts
- Block sender domain and associated IPs at email gateway
- Isolate compromised device from network (if applicable)

---

## 5. Eradication
- Remove phishing email from all user inboxes via O365/G-Suite admin tools
- Remove malicious files or scripts from endpoint
- Conduct vulnerability scan (if email exploited a known CVE)

---

## 6. Recovery
- Restore user access post password reset and endpoint clean-up
- Ensure SIEM and email gateway are logging normally
- Document IOCs and update detection rules (e.g. Splunk, IDS)

---

## 7. Post-Incident Actions
- Root-cause analysis (attack vector & user susceptibility)
- Notify **Tata IT Security Team**, HR (if credential/theft) & Legal (if data disclosure)
- Conduct user awareness training (phishing recognition and reporting)
- Store report in IR database as Case ID XXXX-PHISH-TATA
- Update and refine playbook based on lessons learned

---

## 8. Communication & Escalation Matrix

| Level     | Stakeholder               | Method        |
|----------|---------------------------|---------------|
| Tier 1   | SOC Analyst               | Slack / Email |
| Tier 2   | Tata IT Security Team     | Hotline + Email |
| Tier 3   | CISO                      | Phone / Brief |
| Tier 4   | External Regulators (if breach) | As required |

---

## 9. Tools Used
- Email gateway (Proofpoint / Mimecast / O365 Security)
- Splunk SIEM
- EDR (CrowdStrike / Defender)
- URL scanning (VirusTotal, urlscan)
- Incident ticketing system (ServiceNow)

---

*Created by Dorcas Olujimi*

