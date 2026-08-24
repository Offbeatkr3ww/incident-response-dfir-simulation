# Incident Response & DFIR Simulation - Enterprise Development Environment

> **Portfolio / Training Simulation**  
> This project is entirely fictional. It does not represent access to, participation in, or investigation of any real Rockstar Games systems, breach, or confidential data.

## Overview

This portfolio project documents a simulated enterprise incident-response investigation involving phishing, browser-session theft, VPN control failure, service-account abuse, lateral movement, persistence, trusted-account phishing, build-server compromise, data staging, and a 14.8 GB HTTPS exfiltration event.

The project is designed to demonstrate incident-response decision making rather than exploitation. The investigation focuses on identifying evidence, containing known access paths, reconstructing attacker behavior, communicating risk to leadership, and preserving evidence for Legal and law-enforcement handoff.

## Scenario Summary

The simulated attacker:

1. Phished an employee who used Microsoft 365 on a personal device.
2. Captured reusable authentication/session material after a legitimate MFA event.
3. Reused that identity through a corporate VPN where a temporary contractor exception had left managed-device enforcement in audit-only mode.
4. Reached `DEPLOY-02` and obtained `svc_devops` access from development credential resources.
5. Moved laterally through DEV servers and established persistence with attacker-created accounts and a scheduled task.
6. Compromised Rodriguez's workstation and abused her mailbox to phish Chen.
7. Compromised Chen's workstation and used his legitimate access to reach `BUILD-SRV-04`.
8. Staged, compressed, and exfiltrated approximately 14.8 GB of sensitive development data over HTTPS.
9. Left external attribution to Legal and law enforcement after the company-side investigation preserved the relevant evidence.

## Skills Demonstrated

- Incident response lifecycle and containment prioritization
- Identity, MFA, and session-token analysis
- VPN and device-compliance control analysis
- EDR and Windows event review
- Lateral movement and service-account abuse analysis
- Active Directory and persistence investigation
- Phishing and trusted-account compromise analysis
- Malware behavior interpretation
- Data staging and exfiltration reconstruction
- Evidence preservation and chain-of-custody awareness
- Legal/privacy escalation for personal-device and external-provider evidence
- Executive incident communication and remediation planning

## Evidence Sources Used in the Simulation

- Microsoft 365 / identity sign-in logs
- MFA and session telemetry
- VPN logs
- Windows Security events
- EDR process and credential-access telemetry
- Email message trace and attachment provenance
- SMB / remote service activity
- PowerShell and command-line logging
- File-access auditing
- Firewall / proxy / network-flow telemetry
- Passive DNS, TLS, ASN, and hosting-provider information

## MITRE ATT&CK Coverage

Representative techniques include phishing, user execution, valid accounts, alternate authentication material, remote services, account discovery, credential access, scheduled-task persistence, create account, impair defenses, data staging, archive collected data, and HTTPS exfiltration.

See the full report for the detailed mapping.

## Files

- `Simulated_Incident_Response_DFIR_Case_Study.pdf` - polished portfolio report
- `Simulated_Incident_Response_DFIR_Case_Study.docx` - editable report
- `attack_path.png` - attack-path diagram
- `attack_path.svg` - scalable diagram for GitHub or portfolio use
- `resume_project_entry.txt` - concise résumé-ready project bullets

## Suggested Résumé Entry

**Incident Response & DFIR Simulation - Enterprise Development Environment**

- Led a simulated end-to-end incident response investigation involving phishing, session theft, VPN control failure, service-account abuse, lateral movement, persistence, and 14.8 GB data exfiltration.
- Correlated EDR, Windows, IAM, VPN, firewall, email, and network telemetry to reconstruct the attack path and identify compromised identities and systems.
- Investigated malicious executables, credential access, attacker-created accounts, scheduled-task persistence, security-control changes, data staging, and HTTPS exfiltration.
- Produced executive and technical incident summaries while incorporating containment, evidence preservation, privacy, and Legal escalation considerations.

## Interview Talking Point

A useful way to present this project in an interview is to focus on decision making: how the known access path was contained before attribution, how facts were separated from hypotheses, why personal-device analysis required Legal authorization, and why the environment was described as having the *known intrusion path contained* rather than being declared completely secure before validation was complete.
